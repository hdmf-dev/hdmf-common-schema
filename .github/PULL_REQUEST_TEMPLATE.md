## Follow these steps before creating a PR and then remove this text

Does this PR prepare the schema for a public release?

If YES, then:
1. Remove the suffix "a" from the version string in `conf.py` and `namespace.yaml`
2. Update the date in the release notes
3. Follow release instructions

If NO, then:
  Is the current schema version on "master" a public release?

  If YES, then:
  1. Update the version string in `conf.py` and `namespace.yaml` to the next version with the suffix "a"
  2. Add a new section in the release notes for the new version with the date "Upcoming"
  3. Add release notes for the PR

  If NO, then:
  1. Add release notes for the PR

See https://hdmf-common-schema.readthedocs.io/en/latest/software_process.html for more details.
