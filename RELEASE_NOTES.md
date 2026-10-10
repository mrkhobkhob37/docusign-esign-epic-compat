# Release notes — docusign-esign 3.26.0+epic.1 (Epic compatibility build)

Upstream: https://github.com/docusign/docusign-python-client tag `v3.26.0`
(lightweight tag, commit `502359af7c5cb5066b42e9702899ac5771d2f52f`).

Upstream sdist: `docusign-esign-3.26.0.tar.gz`
(`https://files.pythonhosted.org/packages/4d/7a/5839e5361da8ec5ca5e091a2fa4e76e052415db8696cda052e74063143bc/docusign-esign-3.26.0.tar.gz`,
sha256 `81a7b371030385c5f0e89cdd89e1440fb4842bfc909ec65c7219d2787d5e8012`).

Distribution name `docusign-esign` and import package `docusign_esign`
are unchanged (supporting build, no Group A/B rename). Version is
`3.26.0+epic.1` (frozen in `setup.py:VERSION`).

Changes vs upstream:

- `setup.py`: `VERSION` `3.26.0` -> `3.26.0+epic.1`;
  `REQUIRES` entry `cryptography>=2.5` ->
  `crpt-graph==42.0.5+epic.1` (unconditional requirement; the
  `cryptography` distribution is replaced by `crpt-graph` in the Epic
  dependency closure, so pip would otherwise see a missing requirement).
- `README.md`: fork notice (this build).
- Removed stale generated artifacts shipped in the sdist
  (`docusign_esign.egg-info/`, `PKG-INFO`); they are regenerated at
  build time with the fork version.

Unchanged: `docusign_esign` imports (the package has no direct
`cryptography` imports; `crpt-graph` provides the `cryptography`
package), all other requirements (`urllib3`, `six`, `certifi`,
`python-dateutil`, `setuptools`, `PyJWT`, `nose`), public API. No
decision helper in this build (supporting compatibility builds are not
hooked).

Evidence: prod baseline
(`dep-rewrite-work/baselines/prod-dryrun-report.json`) resolves
`docusign-esign==3.26.0` (requested) with unconditional
`cryptography (>=2.5)`.

License: MIT (upstream LICENSE preserved).
