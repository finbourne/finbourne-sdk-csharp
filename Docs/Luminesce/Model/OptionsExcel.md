# Finbourne.Sdk.Luminesce.Model.OptionsExcel

Additional options applicable to the given SourceType
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ColumnNames** | **string** | Optional | Column Names either overrides the header row or steps in when there is no header row (comma delimited list) |
| **ColumnTypes** | **string** | Optional | Column types (comma delimited list of: &#39;{types}&#39;, some columns may be left blank while others are specified) |
| **InferTypeRowCount** | **int** | Optional | If non-zero and &#39;types&#39; is not specified (or not specified for some columns) this will look through N rows to attempt to work out the column types for columns not pre-specified |
| **NoHeader** | **bool** | Optional | Set this if there is no header row |
| **Calculate** | **bool** | Optional | Whether to attempt a calculation of the imported cell range prior to import |
| **Password** | **string** | Optional | If specified will be used as the password used for password protected workbooks |
| **Worksheet** | **string** | Optional | The worksheet containing the cell range to import (name or index, will default to first) |
| **RangeOrTable** | **string** | Optional | The cell range to import as either a specified range or a table name |
| **IgnoreInvalidCells** | **bool** | Optional | If specified cells which can not be successfully converted to the target type will be ignored |
| **IgnoreBlankRows** | **bool** | Optional | If the entire rows has only blank cells it will be ignored will be ignored |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new OptionsExcel(
    columnNames: "...",  // optional — Column Names either overrides the header row or steps in when there is no header row (comma delimited list)
    columnTypes: "...",  // optional — Column types (comma delimited list of: &#39;{types}&#39;, some columns may be left blank while others are specified)
    inferTypeRowCount: 0,  // optional — If non-zero and &#39;types&#39; is not specified (or not specified for some columns) this will look through N rows to attempt to work out the column types for columns not pre-specified
    noHeader: true,  // optional — Set this if there is no header row
    calculate: true,  // optional — Whether to attempt a calculation of the imported cell range prior to import
    password: "...",  // optional — If specified will be used as the password used for password protected workbooks
    worksheet: "...",  // optional — The worksheet containing the cell range to import (name or index, will default to first)
    rangeOrTable: "...",  // optional — The cell range to import as either a specified range or a table name
    ignoreInvalidCells: true,  // optional — If specified cells which can not be successfully converted to the target type will be ignored
    ignoreBlankRows: true  // optional — If the entire rows has only blank cells it will be ignored will be ignored
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OptionsExcel>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

