# AspireCloud Roadmap

AspirePress is building AspireCloud, which is a mirroring and repository system for WordPress to replace/supplement the
.org repository. This document outlines the roadmap for that product.

**STATUS:** DRAFT (Updated 10/14/2024)

## Terminology

The following terms apply through this document:

- **Mirror** - An endpoint that replicates a list of packages and/or downloadable packages themselves.
- **Repository** - An endpoint that replicates the package data itself.
- **Package** - A package is either a plugin or a theme, which will be distributed by the network.
- **Network** - A loosely federated group of mirrors and repositories that exchange information for the purpose of
  coordinating and providing a comprehensive list of available assets in the WordPress ecosystem.
- **Asset** - An asset is the combined metadata and package information that is hosted by a mirror or repository.
- **Endpoint** - A server or collection of servers that provide compute for the upgrade and install process in
  WordPress.
- **CDN** - A CDN is used to distribute the load of downloading packages and mitigate the risks of malware or denial of service attacks (DDOS).

## Basic functions of mirrors/repositories

A mirror or repository (in this section referred to as a "repository") has the following responsibilities:

- Serve requests from constituents (WordPress instances) that request information about available packages or available
  package updates.
- Provide endpoints for the publication of packages from authors that have authenticated with that repository.
- Distribute metadata about the details of packages, versions of those packages, and where to download those package
  files.
- Receive and update internal records related to authenticated packages from other mirrors.
- Decide which packages to provide and which to hold back.
- Determine which packages to download from the canonical repository, and which to refer to the canonical repository.
- Identify and peer with (or decline to peer with) other repositories.
- Share all information with peer repositories on request.

## WordPress update functionality

The core function of any repository is to provide information on what packages are available for install, either as a
new package or update for an old package. Every mirror must implement a WordPress-compatible API for providing this
information.

Since the APIs are essentially defined within WordPress itself, each repository **MUST** implement the same
specification as WordPress expects. However, the repository _MAY_ provide additional information as part of its
response. That information would be ignored by WordPress.

## Package publication

Package publishers should, with permission of the repository, publish certain packages to the repository through an API.

The specifics of the API are to be determined, but each package maintainer should sign and authenticate their
information for the package, which in turn is validated by the repository as authentic.

Upon receipt of the new package or package version, the repository **MUST** update its internal records to distribute
that version AND call other federated repositories through the associated API endpoints to inform them of the new
version.

## Distributing metadata

When a new package or package version is provided to a repository, it **MUST** call other federated repositories to
inform them of the change within a reasonable period of time.

The specification provides that the repository should try a minimum of three times over twenty-four hours to notify a
repository of the change, in the event that the repository is offline for any reason. This can be accomplished through
queueing and jobs.

If the notification is unsuccessful, the notification process will fail for that repository and inform the owner.
Repositories offline for more than twenty-four hours are assumed to have defederated and are dropped by the cluster.

## Receiving metadata

Upon notification from a peer that a new version is available, and that peer is canonical for the resource, a repository
**must** update its internal records to provide that version of the package within a reasonable timeframe.

There are exceptions to this rule to permit repositories to limit or prohibit distribution of certain packages or
namespaces. However if these restrictions are not defined, a repository must be prepared to offer any and all packages
published by peers.

Upon receipt of the metadata the repository has two choices:

1. Distribute the metadata about the new package/package version with information about where to source the new package;
2. Download a copy of the package for internal and external distribution from the CDN of the repository.

### Metadata Distribution

If a repository (in this case, a mirror) wishes to distribute only the metadata about a particular package, that
metadata **MUST** include an endpoint where the package may be located and acquired.

### Full distribution

For repositories that opt for full distribution, they **MUST** comply with the following rules:

- They must inform other repositories that they are a source (but a non-canonical source) for the package, to ensure
  network durability.
- They must store and check the authenticity and completeness of the package, and reject packages that fail to
  authenticate or are incomplete.
- They must serve the metadata AND the files for the package on request.

## Peering and Network Security

By default, the network is assumed open like the internet. However, this creates some unique security risks.

First, malicious actors could theoretically attempt to publish themselves as sources of packages that are malicious,
even if they are not canonical.

Additionally, malicious peers could attempt to distribute packages that are intentionally malicious or represent
similarity to existing packages to create confusion and permit attack.

To prevent against this, the following rules apply:

- Unless a package comes directly from the original .org repo, the package **MUST** have a namespace. The namespace is
  published by the repository when peering, cannot be changed, and must be provided with any package for which it is
  canonical. For example AspireCloud's first-person repository namespace would be `aspire`.
- Repositories may accept or reject other repositories from which they permit or refuse traffic. Under circumstances
  where a repository is attempting a DDOS attack against the other repositories (e.g. publishing packages that are
  illegitimate for the purposes of flooding other repositories), a repository owner has the right to outright block
  access to their infrastructure by the offending repository.
- A repository may specify what level it accepts from specific repositories. For example, a repository may be accepted
  as a non-canonical source, but refuse to accept canonical packages for security reasons.
- A repository may choose not to distribute ANY packages or assets from a particular repository if it so desires.
- A repository must authenticate requests from repositories through public-private key encryption prior to accepting any
  data or federation from a new repository.
- Repositories may implement review rules and require other repositories to adhere to them for listing of packages in
  their repository.
- Repositories may also implement their own rules and/or review package update information for adherence to their
  rulesets.
- Repositories will always prefer the canonical source over non-canonical sources, and compare checksums of
  non-canonical sources to ensure package security and authenticity.

## Shared information

Peers on the network do not hide information from each other. Any repository may request all metadata regarding the
package information of any other repository. This is to include retained statistics about the package.
