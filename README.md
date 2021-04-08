# hdmf-common

Documentation of the HDMF Common data format specification is available at
[https://hdmf-common-schema.readthedocs.io](https://hdmf-common-schema.readthedocs.io/en/stable/)

## Description

The HDMF Common specification defines a collection of common, reusable data structures
that build the foundation for the modeling of advanced data formats, e.g., the
[Neurodata Without Borders (NWB)](https://www.nwb.org/)
neurophysiology data standard. The HDMF Common schema is integrated with [HDMF](https://github.com/hdmf-dev/hdmf),
which provides advanced APIs for reading, writing, and using hdmf-common data types.

The HDMF-common schema provides the following data structures:

- **DynamicTable :** A column-based table data structure that supports ragged columns and one-to-one and one-to-many relationships
  - **VectorData :** A data structure for representing a column
  - **VectorIndex :** A data structure for indexing a **VectorData**. This is used to store one-to-many relationships
  - **ElementIdentifiers :** A 1D array for storing primary identifiers for elements of a table
- **DynamicTableRegion :** A link from one table to an index or region of another
- **CSRMatrix :** A compressed sparse row matrix

The schema also provides the following base data structures:

- **Data :** An abstract data type for a dataset
- **Container :** An abstract data type for a generic container storing collections of data and metadata
- **SimpleMultiContainer :** A simple container that holds multiple containers

Finally, HDMF-common contains experimental data structures. Prior to adding a new data type to the HDMF-common specification,
new data structures are added to the HDMF-experimental to enable users to experiment with these data structures. Because
these data structures are experimental, they are not guaranteed to maintain backward compatibility, and may never make it into
HDMF-common.

Current experimental data types are:

- **ExternalResources :** A data structure that contains row-based compound-data tables for storing ontology information and
  other external resource references
- **EnumData :** A data structure for representing a column where the data come from a fixed set of elements

