# Finbourne.Sdk.Luminesce.Model.Lineage

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | *No description available.* |
| **Subtype** | **string** | Optional | *No description available.* |
| **LegendText** | **string** | Optional | *No description available.* |
| **Alias** | **string** | Optional | *No description available.* |
| **ColumnTitleTooltip** | **string** | Optional | *No description available.* |
| **ColumnTitleIcon** | **LineageColumnIcon** | Optional | *No description available.* |
| **ExplainTitle** | **string** | Optional | *No description available.* |
| **ExplainTooltip** | **string** | Optional | *No description available.* |
| **ArrowToParentTooltip** | **string** | Optional | *No description available.* |
| **FullFormula** | **string** | Optional | *No description available.* |
| **DocumentationAsHtml** | **string** | Optional | *No description available.* |
| **DocumentationAsMarkDown** | **string** | Optional | *No description available.* |
| **Children** | [List&lt;Lineage&gt;](Lineage.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new Lineage(
    type: "...",  // optional
    subtype: "...",  // optional
    legendText: "...",  // optional
    alias: "...",  // optional
    columnTitleTooltip: "...",  // optional
    columnTitleIcon: ,  // optional
    explainTitle: "...",  // optional
    explainTooltip: "...",  // optional
    arrowToParentTooltip: "...",  // optional
    fullFormula: "...",  // optional
    documentationAsHtml: "...",  // optional
    documentationAsMarkDown: "...",  // optional
    children: new List<Lineage>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Lineage>(json);
```

- [Lineage](Lineage.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

