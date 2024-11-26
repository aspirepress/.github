# Contributing

Contributions are **welcome** and will be fully **credited**.

We accept contributions via Pull Requests on [Github](https://github.com/AspirePress) to the appropriate package.

## Pull Requests

### WordPress Plugins & Projects

For WordPress Plugins and Projects, we ask that you follow these standards:

- Use the [WordPress Coding Standard](https://developer.wordpress.org/coding-standards/wordpress-coding-standards/). You can automate this with [PHPCS](https://github.com/WordPress/WordPress-Coding-Standards), and we recommend you do.
- We ask (but do not require) that you write tests for your contributions. We understand that unit testing the WordPress framework is difficult.
- Please document any changes in behavior inside the pull request so we can easily update the CHANGELOG when we release a new version.
- If your changes break backwards compatibility with the current stable version, it MUST be released as part of the next major version. Please target your Pull Request against the branch for the next major version or, if one is not created, ask that one be created for you. Additionally, any breaking changes should provide a migration between the old version(s) and a new version.
- All code contributed to WordPress-related plugins and projects, _especially_ code that touches the GPL'ed WordPress code, is subject to the GPL as well, and you agree to license your code under the GPL as a condition of committing and merging your code with ours. See the Copyright section below for more.

### For Non-WordPress Libraries & Components

For non-WordPress repositories (e.g. libraries and components that are tangential but do not call into WordPress core),
we apply the following standards:

- We use the [Laminas Coding Standard](https://docs.laminas.dev/laminas-coding-standard/) with certain rules turned off.
- We require tests to be written for code that you commit, and we encourage you to run the tests prior to opening a pull request.
- We require that the code you submit pass PHPStan Level 6 or higher.
- Please document changes you make to the CHANGELOG inside each project, so we know what changes were made, and use that information in your Pull Request.
- Please be sure to document the WHY of your request, not just the WHAT. For example, "Changed class to be more readable" is not a good commit message. "Changed class to be more readable" followed on another line by "The Foo class was hard to read due to some complex logic. I simplified the logic by implementing a bubble sort algorithm, which reduced the complexity and improved the readability" is a much clearer message.
- Please try to keep the first line of your commit message to 80 characters or less, and use subsequent lines to communicate additional information.
- Pull requests should be 10 or fewer files and +/- 500 lines of code. If yours exceeds this, we will want you to explain why, and we may ask you to break up the request into logical parts.
- If your change breaks backwards compatibility, please target the next major version branch. If one has not been created, request that we create it for you. We cannot accept backwards-compatibility breaking changes in the current version, as this violates Semantic Versioning.
- All code contributed is subject to the license of the repository to which it is contributed. You agree to release your code under that license.

## General Rules For Contributing

We welcome contributions. We encourage anyone who wants to contribute to do so. These rules outline our policies in
accepting contributions.

1. Always fork the repository to your own GitHub profile, and do your work in branches there. Do not push branches directly to the AspirePress repository, even if you have access to do so. Note that branches related to releases is perfectly acceptable
2. To contribute your patch, please open a Pull Request, even if you have access to push to `main`. Since you're likely doing your work in your own fork, this makes a pull request more essential.
3. Please make sure your code passes CI/CD before creating a pull request. You can run `make check` locally on most repositories to ensure that they comply with our style, quality and test coverages.
4. Please honor and follow our style guidelines.
5. Please do not merge your own Pull Request. Allow it to be merged by the reviewer once review is complete, or the review has been approved. **If you push new changes after review is approved, it must be reviewed again!** Project leads _may_ merge their own pull requests, but are highly encouraged to seek review from the community, first.
6. Please take feedback seriously, if it's offered. We won't generally reject a pull request on spec, and we will often offer feedback as to why we don't think it's a good fit or what needs to change. If you honor our feedback, we're more likely to accept your pull request.
7. Issues will be closed by the team lead when they have been tested by a quality assurance lead, if available, or another developer. Please do not close issues before they are tested.
8. Remember that this is a) an open-source project run by volunteers and b) an open-source project that you are welcome to fork or work with under the terms of the license. Please feel free to use the code, fork the project, or do what you like, especially if we can't incorporate your recommendations. But please also honor our [Governance Rules](GOVERNANCE.md).

## Branching and Workflow

We use a centralized approach that leaves `main` as the current development version. We also may have a stable branch, version branches for bug and feature fixes in the specific version. Since we use [Semantic Versioning](https://semver.org/) we need to provide ways that we can adequately maintain and/or add features to existing versions, without breaking backwards compatibility.

- The `main` branch is the source of truth for the bleeding edge of the project. It should be used for applying all new features and bugfixes that affect new and existing features.
- The version branch (e.g. `1.x`) is used for bugfixes specific to features in that version.
- Bugfixes that apply to `main` that also apply to a version branch should be applied to `main` and then applied to the version branch. Fixes that apply ONLY to the version branch should target that branch specifically.
- New features should be developed against `main` **first**. If the new feature is applicable to a version branch and the changes in `main` do not break backwards compatibility, you can merge that feature into the version branch.
- Backwards compatibility should always be maintained in version branches **unless** doing so creates a security problem.
- Features must be developed in feature branches that you create in your own [fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo) of the project you're working on. Once the feature is ready, open a pull request against `main` or the version branch if applicable.
- Pull requests should have the commits squashed and merged as a single commit to ease backporting and/or merging upstream.
- We maintain a CHANGELOG in every project that should follow the [Keep A Changelog](https://keepachangelog.com/en/1.1.0/) specification. For unreleased changes, keep an " Unreleased" section in the changelog. Update the changelog to the version you plan to deploy BEFORE tagging and move unreleased changes to that changelog. Make sure that you update ALL OTHER BRANCHES (`main` and version branches) with the changelog information so that the changelog is consistent.
- Once a feature branch is merged into the main project or a version branch, it _should not_ be used again. It should be deleted and a new feature branch started from the latest version of the project.
- Once `main` begins to drift significantly from a version branch, such that it becomes difficult or impossible to merge items from `main` into the version branch, that version is considered discontinued and we should be making plans for a new major version.
- When a new major version is issued, we need to create a version branch with that major version's revision number (e.g. `2.x`) for future development. We do not do minor version branches.

## Licenses and Copyrights

### Plain English

Legal language can be tricky. Here is what our legal terms are, in plain English. Anywhere that these plain English terms conflict with the legal terms, the legal terms take precedence.

* When you contribute code, you still own the code, but we are free to use it forever.
* Contributing code to the project does not automatically mean that the end product will be suitable for a particular purpose you may have.
* If your contribution causes us harm, and you could have prevented it, you are responsible for the harm. An example would be including code you know to be owned by someone else.
* We only allow copyleft (GPL and similar) licensed libraries to be used in our copyleft-licensed projects. We don't allow copyleft licenses in non-copyleft projects.
* We may choose a different license for any project at any time, without asking. But we won't make any open source project into a closed-source one.
* Some users may ask us for a special license that doesn't conflict with the original license but adds new terms. This "dual licensing" is permissible.
* If we dual license something, we won't restrict others from using the software the way it was originally intended to be used.
* You promise us that you're not breaking any laws, contracts or agreements that you have regarding code you contribute.

### Legal Terms

These terms are legally binding on contributors and AspirePress alike. By contributing to AspirePress, you agree to these terms.

If you contribute to this project, you grant an exclusive, royalty-free, global, irrevocable license to AspirePress and any members of AspirePress to use, relicense, redistribute, copy, modify, change or otherwise utilize any source code you contribute. Furthermore, contribution of source code is not a guarantee that you will be granted rights to use the project for your own purposes. By contributing you acknowledge that the code you contribute becomes licensed by AspirePress, and you may not revoke, rescind, or modify that license at any time for any reason.

You also agree to indemnify and hold harmless AspirePress and any members of AspirePress from any harm, including litigation or copyright enforcement, for code you commit that you do not own. **DO NOT COMMIT CODE YOU DO NOT OWN OR THAT IS COPYRIGHTED BY SOMEONE ELSE!**

When contributing code or libraries to AspirePress, you agree that you will not contribute a CopyLeft-licensed component to a non-CopyLeft project (e.g, no GPL libraries in MIT-licensed projects). If we are already licensing a project under a CopyLeft license, this rule does not apply.

Your license of your contributions to AspirePress grants us the right to relicense any project or repository under new terms, starting with the next major version. However, we voluntarily limit our relicensing rights to relicensing projects only insofar as the new license is no more restrictive than the previous license. We reserve the right to convert any non-CopyLeft licensed code into a CopyLeft-licensed project, though we will use this right sparingly. You agree that your permission is not needed for relicensing of a project that you contributed to.

Note that we may "dual license" any project at any time. A "dual license" may require certain users to use a particular license based on conditions within that license; all others may use the original or new (but similarly restrictive) license. The "dual license" model does not in any way constitute a reduction in rights or freedoms granted users, and any user that wishes to remain on an older version under the original license may do so. We will not retroactively change license terms.

When creating a pull requests or committing changes to any AspirePress repository, you certify that your contributions are your own, are original and do not violate the intellectual property of any other person or entity. You also certify that you are not violating any license agreements or contracts that you have with any person or entity. You also agree that any contributions may be licensed under any license deemed appropriate by AspirePress, including but not limited to open source, closed source, proprietary or custom licenses, and that such license terms neither violate your rights or your copyright to the contributions. You also certify that any previous contributions shall be deemed subject to the terms of the version in effect on the date and time of a pull request, or any future revisions for pull requests you may submit.

## Misc

The terms of this contribution agreement may change at any time, and will be published in GitHub and made public. Changes are effective immediately for new contributions, and thirty days (30 days) after posting the new terms to GitHub.com for existing contributions. You may opt out of the new terms by contacting any person on the leadership team or writing support@aspirepress.org.

You can view our [list of contributors](CREDITS.md).
