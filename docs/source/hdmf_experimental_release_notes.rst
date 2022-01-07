.. _hdmf_experimental_release_notes:

hdmf-experimental Release Notes
===============================

0.2.0 (January 7, 2022)
-----------------------
- In the experimental ``ExternalResources``, added ``relative_path`` field to the "objects" table dtype. This is used in
  place of the previous ``field`` field representing the relative path to get to the dataset/attribute from the object.
  The previous ``field`` field will be used to represent a compound type field name if the dataset/attribute is a
  compound dtype.
- Updated contributors

0.1.0 (March 29, 2021)
----------------------
- See the release notes for :ref:`hdmf-common 1.4.0 <hdmf_common_release_notes>` for details.
