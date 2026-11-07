# ShipLens 0.3.0-rc.1 source delivery

This source-only set accompanies source commit `554f63e1580aa17a1a7314cb3bb21ce9e4c11740` and OCI manifest `sha256:6d9a3f856ee73f10a06732ffb42d3fa028af86176aa365245214a6bfec828d00` (archive SHA-256 `06c1491502c71f43df70342916023ed0239459d1a8b4cc9938dea2e72b45616f`). It contains no OCI image or executable Node binary distribution.

Verify the downloaded files before using them:

```sh
sha256sum --check SHA256SUMS
```

On macOS, use `shasum -a 256 -c SHA256SUMS`. `SOURCE-MANIFEST.json` identifies both archives and every runtime-source archive member. Each member was independently read back and SHA-256 checked. The application archive is the unchanged curated source package for this commit; it contains the ShipLens license, contributor notices, source, lockfile and build instructions without Git history.

The runtime-source archive contains all 63 exact Debian source/version part sets for the 88 installed Debian packages, including each `.dsc` and every file listed by its authenticated SHA-256 part set. Original source-part filenames and upstream bytes are preserved. Signed Debian InRelease files, source/binary indexes and the authorized public keys accompany the package-to-source mapping. Signed Packages plus installed-package metadata establishes a release source/version correspondence; it does not establish that every installed byte equals a Debian binary package.

Node v24.22.2 source, signed SHASUMS, the release public-key ring and public build documentation accompany the set. The retained official binary matches the signed upstream checksum, and its Node executable and license match the image. That verifies upstream identity; it is not a reproducible-build result or a release-job attestation. For example, verify the clear-signed checksum list with `gpgv --keyring ./node/keys/pubring.kbx --output SHASUMS256.txt ./node/SHASUMS256.txt.asc` after independently checking the authorized release-key fingerprints. Use the resulting list to check the source archive. Public build/configuration files describe the upstream build; they do not assert a particular release machine or job.

`notices/` preserves the exact selected image notice bytes. The manifest maps every copied notice to image-relative paths, including Debian copyright files, common license texts, Node's bundled license, and installed runtime and browser-build dependency notices. A shared copyright file is included once with all contributing package mappings retained. Three installed AWS SDK package paths lacked directly copied package notices; those entries remain an inventory disclosure. The complete Apache-2.0 license and Amazon2018 attribution already occur in the shared AWS notice collections. Apache-2.0 section 4(a) does not require a copy in every package directory, and no omitted upstream NOTICE from these exact three packages was established under section 4(d). No replacement notices are invented and no blanket legal clearance is implied. All TypeScript notice text remains intact. The compiled browser payload in this image includes the full React/ReactDOM/Scheduler MIT notice and attribution.

The application remains Apache-2.0 with its existing contributor attribution. Third-party terms continue to apply to their respective components. The 215 raw Debian scanner rows (211 remaining unresolved after separate applicability review) and other licensing review boundaries remain recorded; this set is not a blanket legal or security clearance.

Publication and anonymous recipient access are pending approval of these exact files and the source-only delivery channel. A private retained bundle or a URL proposal alone does not establish public corresponding-source access or an accepted source offer. Source delivery does not authorize OCI image publication, deployment, hosted use or production readiness. Original managed-image inspection and all existing release holds remain open.
