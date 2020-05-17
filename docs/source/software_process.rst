Making a Pull Request
=====================

Actions to take on each PR (this is also in ``.github/PULL_REQUEST_TEMPLATE.md``):

If the PR prepares the schema for a public release, then:

1. Remove the suffix "a" from the version string in ``conf.py`` and ``namespace.yaml``
2. Update the date in the release notes
3. Follow release instructions (see next section)

If not, then:

  If the current schema version on "master" is a public release, then:

  1. Update the version string in ``conf.py`` and ``namespace.yaml`` to the next version with the suffix "a"
  2. Add a new section in the release notes for the new version with the date "Upcoming"
  3. Add release notes for the PR

  If not, then:

  1. Add release notes for the PR

Merging PRs and Making Releases
===============================

**Public release**: a tagged release of the schema. The version string MUST NOT end with "a". The current "dev"
branch of HDMF and all HDMF releases MUST point to a public release of hdmf-common-schema. All schema that use
hdmf-common-schema as a submodule MUST also point only to public releases.

**Internal release**: a state of the schema "master" branch where the version string ends with "a".

The default branch of hdmf-common-schema is "master". The "master" branch holds the bleeding edge version of
the hdmf-common schema specification.

PRs should be made to "master". Every PR should include an update to ``/docs/source/format_release_notes.rst``.
If the current version is a public release, then the PR should also update the version of the schema in two places:
``/docs/source/conf.py`` and ``/common/namespace.yaml``. The new version should be the next bugfix/minor/major version
of the schema with the suffix "a" (for "alpha"). For example, if the current schema on "master" has version "2.2.0",
then a PR implementing a bug fix should update the schema version from "2.2.0" to "2.2.1a". Appending the "a" suffix
ensures that any person or API accessing the default "master" branch of the repo containing an internal release of the
schema receives the schema with a version string that is distinct from public releases of the schema. If the current
schema on "master" is already an internal release, then the version string does not need to be updated unless the PR
requires an upgrade in the version (e.g., from bugfix to minor).

Before merging a PR on hdmf-common-schema, developers should test their changes locally with the latest version of HDMF
to ensure compatibility. If changes are required in HDMF in order for the changes in hdmf-common-schema to work, then
the changes in HDMF should be implemented and tested locally *before* merging the PR in hdmf-common-schema. This
workflow ensures that changes in HDMF can be implemented and no further changes to the schema are required.

HDMF should contain a branch and PR that tracks and is compatible with the "master" branch of hdmf-common-schema. Before
a public release of hdmf-common-schema is made, this HDMF branch should be checked to ensure that when the new release
is made, the branch can be merged without issue.

Immediately prior to making a new public release, the version of the schema should be updated to remove the "a" suffix
and the documentation and release notes should be updated as needed (see next section).

The current "dev" branch of HDMF and all HDMF releases MUST always point to a public release of hdmf-common-schema. If
a public release contains an internally released version of hdmf-common-schema, e.g., from an untagged commit on the
"master" branch, then it will be difficult to find the version (commit) of hdmf-common-schema that was used to create
an HDMF file when the schema is not cached.

Making a Release Checklist
==========================

Copy the following to the GitHub PR in hdmf-common-schema that prepares the schema for public release and then follow
the steps in the checklist.

.. code-block::

  Before merging:
  - [ ] Update requirements versions as needed
  - [ ] Update legal file dates and information in ``Legal.txt``, ``license.txt``, ``README.rst``, ``conf.py``, and any other locations as needed
  - [ ] Update README as needed
  - [ ] Update the version string in ``conf.py`` and ``namespace.yaml``
  - [ ] Update ``conf.py`` as needed
  - [ ] Update release notes and relevant docs
  - [ ] Test docs locally (``make fulldoc``)
  - [ ] Push changes to a new PR and make sure all PRs to be included in this release have been merged
  - [ ] Point the HDMF submodule to this branch in the HDMF branch corresponding to this schema version and run HDMF tests
  - [ ] Check that the readthedocs build for this PR succeeds (build latest to pull the new branch, then activate and build docs for new branch):
    https://readthedocs.org/projects/hdmf-common-schema/builds/

  After merging:
  - [ ] Create release on GitHub releases page with release notes
  - [ ] Check that the readthedocs "latest" and "stable" builds run and succeed

  The time between merging this PR and creating a new public release should be minimized.
