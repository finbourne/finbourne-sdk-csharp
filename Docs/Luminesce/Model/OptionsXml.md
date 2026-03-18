# Finbourne.Sdk.Luminesce.Model.OptionsXml

Additional options applicable to the given SourceType
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ColumnTypes** | **string** | Optional | Column types (comma delimited list of: &#39;{types}&#39;, some columns may be left blank while others are specified) |
| **InferTypeRowCount** | **int** | Optional | If non-zero and &#39;types&#39; is not specified (or not specified for some columns) this will look through N rows to attempt to work out the column types for columns not pre-specified |
| **ValuesToMakeNull** | **string** | Optional | Regex of values to map to &#39;null&#39; in the returned data. |
| **ColumnNames** | **string** | Optional | Column Names either overrides the header row or steps in when there is no header row (comma delimited list) |
| **NodePath** | **string** | Optional | XPath query that selects the nodes to map to rows |
| **Namespaces** | **string** | Optional | Selected prefix(es) and namespace(s):prefix1&#x3D;namespace1-uri1,prefix2&#x3D;namespace2-uri2,...prefixN&#x3D;namespaceN-uriN |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new OptionsXml(
    columnTypes: "...",  // optional — Column types (comma delimited list of: &#39;{types}&#39;, some columns may be left blank while others are specified)
    inferTypeRowCount: 0,  // optional — If non-zero and &#39;types&#39; is not specified (or not specified for some columns) this will look through N rows to attempt to work out the column types for columns not pre-specified
    valuesToMakeNull: "...",  // optional — Regex of values to map to &#39;null&#39; in the returned data.
    columnNames: "...",  // optional — Column Names either overrides the header row or steps in when there is no header row (comma delimited list)
    nodePath: "...",  // optional — XPath query that selects the nodes to map to rows
    namespaces: "..."  // optional — Selected prefix(es) and namespace(s):prefix1&#x3D;namespace1-uri1,prefix2&#x3D;namespace2-uri2,...prefixN&#x3D;namespaceN-uriN
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OptionsXml>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

