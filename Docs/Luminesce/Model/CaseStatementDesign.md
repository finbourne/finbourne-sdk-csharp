# Finbourne.Sdk.Luminesce.Model.CaseStatementDesign

Representation of the selected field and a list of: filter, source, and target.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SelectedField** | **string** | Optional | Selected field in the SQL query. |
| **CaseStatementItems** | [List&lt;CaseStatementItem&gt;](CaseStatementItem.md) | Optional | A list containing the filter, source, and target. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new CaseStatementDesign(
    selectedField: "...",  // optional — Selected field in the SQL query.
    caseStatementItems: new List<CaseStatementItem>()  // optional — A list containing the filter, source, and target.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CaseStatementDesign>(json);
```

- [CaseStatementItem](CaseStatementItem.md) — used in `CaseStatementItems`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

