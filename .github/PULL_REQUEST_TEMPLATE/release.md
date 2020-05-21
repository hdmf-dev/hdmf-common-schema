# Prepare a release

Before merging:
- [ ] Update requirements versions as needed
- [ ] Update legal file dates and information in `Legal.txt`, `license.txt`, `README.rst`, `docs/source/conf.py`,
  and any other locations as needed
- [ ] Update README as needed
- [ ] Update the version string in `docs/source/conf.py` and `common/namespace.yaml` (remove "-alpha" suffix)
- [ ] Update `docs/source/conf.py` as needed
- [ ] Update release notes (set release date) in `docs/source/format_release_notes.rst` and any other docs as needed
- [ ] Test docs locally (`make fulldoc`)
- [ ] Push changes to this PR and make sure all PRs to be included in this release have been merged
- [ ] Point the HDMF submodule to this branch in the HDMF branch corresponding to this schema version and run HDMF tests
- [ ] Check that the readthedocs build for this PR succeeds (build latest to pull the new branch, then activate and
  build docs for new branch): https://readthedocs.org/projects/hdmf-common-schema/builds/

After merging:
1. Create release on GitHub releases page with release notes
2. Check that the readthedocs "latest" and "stable" builds run and succeed

See https://hdmf-common-schema.readthedocs.io/en/latest/software_process.html for more details.
