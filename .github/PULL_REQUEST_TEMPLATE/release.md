Prepare for release of hdmf-common-schema [version]

### Before merging:
- [ ] Update requirements versions as needed
- [ ] Update legal file dates and information in `Legal.txt`, `license.txt`, `README.rst`, `docs/source/conf.py`,
  and any other locations as needed
- [ ] Update `README.md` as needed
- [ ] Update the version string in `docs/source/conf.py` and `common/namespace.yaml` (remove "-alpha" suffix)
- [ ] Update `docs/source/conf.py` as needed
- [ ] Update release notes (set release date) in `docs/source/format_release_notes.rst` and any other docs as needed
- [ ] Test docs locally (`make fulldoc`). Note: if the schema has been changed, then the local copy of HDMF must contain
  the latest changes in hdmf-common-schema in the git submodule in order for the schema changes to be reflected in the
  docs.
- [ ] Push changes to this PR and make sure all PRs to be included in this release have been merged
- [ ] Point the HDMF submodule to this branch in the HDMF branch corresponding to this schema version and run HDMF tests
- [ ] Check that the readthedocs build for this PR succeeds (build latest to pull the new branch, then activate and
  build docs for new branch): https://readthedocs.org/projects/hdmf-common-schema/builds/

### After merging:
1. Create a new git tag. Pull the latest master branch locally, run `git tag [version] --sign`, copy and paste the
   release notes into the tag message, and run `git push --tags`.
2. On the [GitHub tags page](https://github.com/hdmf-dev/hdmf-common-schema/tags) page, click "Create release" to
   create a release from the new tag. Copy and paste the release notes into the release message and update the title
   to the version string.
3. Check that the readthedocs "latest" and "stable" builds run and succeed
4. A new version of HDMF should be released that uses the latest schema release and the schema readthedocs should be
   rebuilt. Then schema changes will be reflected in the docs. This is due to a dependency between the docs and the
   API.

See https://hdmf-common-schema.readthedocs.io/en/latest/software_process.html for more details.
