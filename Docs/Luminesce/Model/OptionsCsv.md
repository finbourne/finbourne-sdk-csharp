# Finbourne.Sdk.Luminesce.Model.OptionsCsv

Additional options applicable to the given SourceType
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ColumnNames** | **string** | Optional | Column Names either overrides the header row or steps in when there is no header row (comma delimited list) |
| **ColumnNamesWanted** | **string** | Optional | Column (by Name) that should be returned (comma delimited list) |
| **ColumnTypes** | **string** | Optional | Column types (comma delimited list of: &#39;{types}&#39;, some columns may be left blank while others are specified) |
| **InferTypeRowCount** | **int** | Optional | If non-zero and &#39;types&#39; is not specified (or not specified for some columns) this will look through N rows to attempt to work out the column types for columns not pre-specified |
| **NoHeader** | **bool** | Optional | Set this if there is no header row |
| **Delimiter** | **string** | Optional | The delimiter between values (\\t for tab) |
| **Escape** | **string** | Optional | Character used to escape the &#39;Quote&#39; character when within a value |
| **Quote** | **string** | Optional | Character used around any field containing the &#39;delimiter&#39; or a line break. |
| **ValuesToMakeNull** | **string** | Optional | Regex of values to map to &#39;null&#39; in the returned data. |
| **SkipPreHeader** | **int** | Optional | Number of rows to ignore before the header row |
| **SkipPostHeader** | **int** | Optional | Number of rows to ignore after the header row |
| **SkipInvalidRows** | **bool** | Optional | Skip invalid data rows (totally invalid ones),  This also allows for potentially wrong data if it can be handled somewhat e.g. embedded quotes misused (and still returns such rows). In either case a warning will show in the progress feedback. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new OptionsCsv(
    columnNames: "...",  // optional — Column Names either overrides the header row or steps in when there is no header row (comma delimited list)
    columnNamesWanted: "...",  // optional — Column (by Name) that should be returned (comma delimited list)
    columnTypes: "...",  // optional — Column types (comma delimited list of: &#39;{types}&#39;, some columns may be left blank while others are specified)
    inferTypeRowCount: 0,  // optional — If non-zero and &#39;types&#39; is not specified (or not specified for some columns) this will look through N rows to attempt to work out the column types for columns not pre-specified
    noHeader: true,  // optional — Set this if there is no header row
    delimiter: "...",  // optional — The delimiter between values (\\t for tab)
    escape: "...",  // optional — Character used to escape the &#39;Quote&#39; character when within a value
    quote: "...",  // optional — Character used around any field containing the &#39;delimiter&#39; or a line break.
    valuesToMakeNull: "...",  // optional — Regex of values to map to &#39;null&#39; in the returned data.
    skipPreHeader: 0,  // optional — Number of rows to ignore before the header row
    skipPostHeader: 0,  // optional — Number of rows to ignore after the header row
    skipInvalidRows: true  // optional — Skip invalid data rows (totally invalid ones),  This also allows for potentially wrong data if it can be handled somewhat e.g. embedded quotes misused (and still returns such rows). In either case a warning will show in the progress feedback.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OptionsCsv>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

