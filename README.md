# thp-fhir-registry

Private FHIR IG registry for Trifork Health Platform.

Holds `fhir-ig-list.json`, the cross-IG directory the HL7 FHIR IG Publisher
reads and writes during `-go-publish`. Each entry maps an IG's canonical URL
to its rendered site, version history, and CI build, so the publisher can
resolve cross-IG references and announce new releases.

Forked and trimmed from [FHIR/ig-registry](https://github.com/FHIR/ig-registry).

## How entries get here

Written automatically by each Trifork IG repo's publish workflow (e.g.
`trifork/anchor-ig`). The workflow checks this repo out, runs the IG
Publisher, and commits the updated `fhir-ig-list.json` back to `master` when
`registry-commit: true`.

Manual edits should be rare. Keep the JSON valid — the publisher refuses to
read a malformed file.

For the entry-field reference, see the upstream
[README](https://github.com/FHIR/ig-registry/blob/master/README.md).
