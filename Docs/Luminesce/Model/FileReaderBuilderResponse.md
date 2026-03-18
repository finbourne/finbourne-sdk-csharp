# Finbourne.Sdk.Luminesce.Model.FileReaderBuilderResponse

Information on how to construct a file-read sql query
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Query** | **string** | Optional | The generated SQL |
| **Error** | **string** | Optional | The error from running generated SQL Query, if any |
| **Columns** | [List&lt;ColumnInfo&gt;](ColumnInfo.md) | Optional | Column information for the results |
| **Data** | **Object** | Optional | The resulting data from running the Query |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new FileReaderBuilderResponse(
    query: "...",  // optional — The generated SQL
    error: "...",  // optional — The error from running generated SQL Query, if any
    columns: new List<ColumnInfo>(),  // optional — Column information for the results
    data:   // optional — The resulting data from running the Query
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FileReaderBuilderResponse>(json);
```

- [ColumnInfo](ColumnInfo.md) — used in `Columns`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

