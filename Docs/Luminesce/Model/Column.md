# Finbourne.Sdk.Luminesce.Model.Column

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IsPrimaryKey** | **bool** | Optional | *No description available.* |
| **IsMain** | **bool** | Optional | *No description available.* |
| **IsRequiredByProvider** | **bool** | Optional | *No description available.* |
| **MandatoryForActions** | **string** | Optional | *No description available.* |
| **Lineage** | [Lineage](Lineage.md) | Optional | *No description available.* |
| **Name** | **string** | Optional | *No description available.* |
| **Type** | **DataType** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **DisplayName** | **string** | Optional | *No description available.* |
| **ConditionUsage** | **ConditionAttributes** | Optional | *No description available.* |
| **SampleValues** | **string** | Optional | *No description available.* |
| **AllowedValues** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new Column(
    isPrimaryKey: true,  // optional
    isMain: true,  // optional
    isRequiredByProvider: true,  // optional
    mandatoryForActions: "...",  // optional
    lineage: new Lineage(...),  // optional
    name: "...",  // optional
    type: ,  // optional
    description: "...",  // optional
    displayName: "...",  // optional
    conditionUsage: ,  // optional
    sampleValues: "...",  // optional
    allowedValues: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Column>(json);
```

- [Lineage](Lineage.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

