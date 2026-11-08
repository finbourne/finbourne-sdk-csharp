# Finbourne.Sdk.Luminesce.Model.ExportConditionalRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Operator** | **ExportRuleOperator** | Required | *No description available.* |
| **Value** | **string** | Optional | *No description available.* |
| **ValueTo** | **string** | Optional | *No description available.* |
| **ValueColumn** | **string** | Optional | *No description available.* |
| **ValueToColumn** | **string** | Optional | *No description available.* |
| **SourceColumn** | **string** | Optional | *No description available.* |
| **Effect** | **ExportRuleEffect** | Required | *No description available.* |
| **Color** | **ExportRuleColor** | Optional | *No description available.* |
| **Hex** | **string** | Optional | *No description available.* |
| **Text** | **string** | Optional | *No description available.* |
| **Format** | **string** | Optional | *No description available.* |
| **IncludeAggregates** | **bool** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ExportConditionalRule(
    varOperator: ,  // required
    value: "...",  // optional
    valueTo: "...",  // optional
    valueColumn: "...",  // optional
    valueToColumn: "...",  // optional
    sourceColumn: "...",  // optional
    effect: ,  // required
    color: ,  // optional
    hex: "...",  // optional
    text: "...",  // optional
    format: "...",  // optional
    includeAggregates: true  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExportConditionalRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

