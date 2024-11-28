# AspirePress Cloud Publishing Policy

## Preamble

The goal of Aspire Cloud Repository is to provide a robust distributed source for downloading software for extending WordPress and related compatible CMSs. The Distributed Software Repository project is released freely in order to establish a network of trusted repositories which democratize software distribution free from the control of any one person or organization.

This DRAFT policy governs what software will be accepted to host on AspirePress Cloud. At the project's inception, we are providing a general list of requirements and deferring to the corresponding [guidelines available at wordpress.org](https://developer.wordpress.org/plugins/wordpress-org/detailed-plugin-guidelines/) for interpretation until they have been fully rewritten in this document. While this document is in draft form, in case of conflicts or updates, the guideline explanations below will supersede any others.

If you believe you have a case where a software package would not be accepted for hosting on wordpress.org, but believe it should be allowed on Aspire Cloud, please contact support@aspirepress.org.

While this Preamble should help understand and interpret the Hosting Policy, it is not a formal part of Policy.

-----

## Aspire Cloud Guidelines, Terms, & Conditions

### Licensing & Other Requirements

1. Plugins and themes MUST be distributed under a license that is compatible with the GNU General Public License version 2 or higher. The GPL and MIT licenses are recommended, but [any license from GNU.org's list of compatible licenses](https://www.gnu.org/licenses/license-list.en.html#GPLCompatibleLicenses) is acceptable.
2. By submitting your software and updates, you agree to indemnify and hold harmless AspirePress and its network partners for any actions resulting from your software.
3. Source code must be reasonably human-readable, and must not be minified, obfuscated, compressed, or generated at runtime.
4. All software must respect trademarks, copyrights, and project names. You warrant that the software you upload complies with this condition and that you are authorized to distribute it.
5. A complete stable version of the software must be available at the time of submission from its canonical repository.

### Features & Functions Not Permitted

6. Trialware is not permitted. Plugins and themes may not disable any of their own functionality after any trial period has ended.
7. Plugins and themes may not track users without their explicit consent, and must offer a means for the user to opt out.
8. Source code for plugins and themes MUST be self-contained, and MUST NOT download or execute any additional code from external systems.

### Best Practice Guidelines

9. Plugins and themes should not hijack the admin dashboard.
10. Plugins and themes should use libraries already bundled with installed software, whenever available. (e.g., jQuery is bundled with WordPress)
11. Frequent commits to a plugin or theme should be avoided. Bundle multiple updates together at a reasonable release cadence. Developers themes MUST NOT publish version updates for the purpose of increasing visibility. Patches for security and bug fixes are allowed any time.
12. Plugin and theme version numbers must be incremented for each new release. Semantic versioning is encouraged but not required, provided the version numbers can be easily parsed to compare versions.

### Additional Conditions & Permission

13. We reserve the right to decline any software package not in the best interest of the community, at our sole discretion. This includes but is not limited to so-called "nulled" software, software which may be illegal in certain jurisdictions, software whose intended use would violate the AspirePress Code of Conduct, software which violates the terms of its licensing, or software which is forked in a manner which is substantially divisive to the community.
14. We reserve the right to take any action deemed necessary to maintain the integrity and security of the Plugin and Theme directories, including but not limited to the suspension or removal of content that negatively impacts the operation of these directories.
15. Software as a Service is permitted.
16. The use of third-party APIs is permitted, subject to applicable privacy legislation in the jursidiction of the user.
17. The use of third-party CDN services for fonts or similar assets including javascript, but be aware that in certain cases these may conflict with privacy laws in some regions. For this reason we recommend that all such resources be bundled with the software.

### Community Requirements

18. Software contributors are expected to abide by the [AspirePress Code of Conduct](code_of_conduct.md).
19. Public-facing pages in the software directory (e.g., readme files) must not use spammy language or excessive external links.
20. Plugins and themes may not embed external links or credits on the public site without explicitly asking the user’s permission.
21. Plugins and themes may not include affiliate links or similar codes which provide revenue to the developer without disclosing them, and must allow users to opt out or change the affiliate code if they wish.

