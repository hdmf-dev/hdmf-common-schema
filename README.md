# hdmf-common
Specifications for pre-defined data structures of [HDMF](https://github.com/hdmf-dev/hdmf)

The HDMF-common schema provides the following data structures:
- DynamicTable : a column-based table structure that stores one-to-one and one-to-many relationships
  - VectorData : a data structure for representing a column
  - VectorIndex : a data structure for indexing a VectorData. This is used to store one-to-many relationships
  - ElementIdentifiers : a 1D array for storing primary identifiers for elements of a table
- DynamicTableRegion : a link from one table to an index or region of another
- CSRMatrix : a compressed sparse row matrix

The schema also provides the following base data structures:
- Data : an abstract data type for a dataset
- Index : an abstract pointer that indexes data values
- Container : an abstract data type for a generic container storing collections of data and metadata
