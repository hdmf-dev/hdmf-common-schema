# Prepare a release

Before merging:
- [ ] Update requirements versions as needed
- [ ] Update legal file dates and information in ``Legal.txt``, ``license.txt``, ``README.rst``, ``conf.py``, and any other locations as needed
- [ ] Update README as needed
- [ ] Update the version string in ``conf.py`` and ``namespace.yaml`` (remove "-alpha" suffix)
- [ ] Update ``conf.py`` as needed
- [ ] Update release notes (set release date) and relevant docs
- [ ] Test docs locally (``make fulldoc``)
- [ ] Push changes to a new PR and make sure all PRs to be included in this release have been merged
- [ ] Point the HDMF submodule to this branch in the HDMF branch corresponding to this schema version and run HDMF tests
- [ ] Check that the readthedocs build for this PR succeeds (build latest to pull the new branch, then activate and build docs for new branch):
  https://readthedocs.org/projects/hdmf-common-schema/builds/

After merging:
1. Create release on GitHub releases page with release notes
2. Check that the readthedocs "latest" and "stable" builds run and succeed

See https://hdmf-common-schema.readthedocs.io/en/latest/software_process.html for more details.
