Prepare for release of hdmf-common-schema [version]

### Before merging:
- [ ] Update requirements versions as needed
- [ ] Update legal file dates and information in `Legal.txt`, `license.txt`, `README.md`, `docs/source/conf.py`,
  and any other locations as needed
- [ ] Update `README.md` as needed
- [ ] Update the version string in `docs/source/conf.py` and `common/namespace.yaml` (remove "-alpha" suffix)
- [ ] Update `docs/source/conf.py` as needed
- [ ] Update release notes (set release date) in `docs/source/hdmf_common_release_notes.rst`,
  `docs/source/hdmf_experimental_release_notes.rst`, and any other docs as needed
- [ ] Test docs locally (`cd docs; make fulldoc`) where the hdmf-common-schema submodule in the local version of HDMF
  is fully up-to-date with the head of the main branch.
- [ ] Push changes to this PR and make sure all PRs to be included in this release have been merged
- [ ] Check that the readthedocs build for this PR succeeds (build latest to pull the new branch, then activate and
  build docs for new branch): https://readthedocs.org/projects/hdmf-common-schema/builds/

### After merging:
1. Create a new git tag. Pull the latest master branch locally, run `git tag [version] --sign`, copy and paste the
   release notes into the tag message, and run `git push --tags`.
2. On the [GitHub tags page](https://github.com/hdmf-dev/hdmf-common-schema/tags) page,
   click "..." -> "Create release" for the new tag on the right side of the page.
   Copy and paste the release notes into the release message, update the formatting if needed (reST to Markdown),
   and set the title to the version string.
3. Check that the readthedocs "latest" and "stable" builds run and succeed. Delete the readthedocs build for the
   merged PR. https://readthedocs.org/projects/hdmf-common-schema/builds/
4. Update the HDMF submodule in the HDMF branch corresponding to this schema version to point to the tagged commit.

See https://hdmf-common-schema.readthedocs.io/en/latest/software_process.html for more details.
