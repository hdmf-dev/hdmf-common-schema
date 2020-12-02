hdmf-common Release Notes
=========================

1.3.0 (Upcoming)
-------------------------

- Add data type ``ExternalResources`` for storing ontology information / external resource references. NOTE: this
  data type is in beta testing and is subject to change in a later version.
- Changed dtype for datasets within ``CSRMatrix`` from 'int' to 'uint'. Negative values do not make sense for these
  datasets.

1.2.1 (November 4, 2020)
------------------------

- Update software process documentation for maintainers.
- Fix missing data_type_inc for ``CSRMatrix``. It now has ``data_type_inc: Container``.
- Add ``hdmf-schema-language`` comment at the top of each yaml file.
- Add ``SimpleMultiContainer``, a Container for storing other Container and Data objects together

1.2.0 (July 10, 2020)
------------------------

- Add software process documentation.
- Fix missing dtype for ``VectorIndex``.
- Add new ``VocabData`` data type.
- Move ``Data``, ``Index``, and ``Container`` to base.yaml. This change does not functionally change the schema.
- ``VectorIndex`` now extends ``VectorData`` instead of ``Index``. This change allows ``VectorIndex`` to index other
  ``VectorIndex`` types.
- The ``Index`` data type is now unused and has been removed.
- Fix documentation for ragged arrays.

1.1.3 (January 21, 2020)
------------------------

- Fix missing 'shape' and 'dims' key for types ``VectorData``, ``VectorIndex``, and ``DynamicTableRegion``.

1.1.2 (January 9, 2020)
-----------------------

- Fix version number in namespace.yaml and docs

1.1.1 (January 9, 2020)
-----------------------

- Support for ReadTheDocs continuous documentation was added, and legal/license documents were also added. The schema is
  unchanged.

1.1.0 (January 3, 2020)
-----------------------

- The 'colnames' attribute of ``DynamicTable`` changed from data type 'ascii' to 'text'.
- Improved documentation and type docstrings.

1.0.0 (September 26, 2019)
--------------------------

Initial release.
