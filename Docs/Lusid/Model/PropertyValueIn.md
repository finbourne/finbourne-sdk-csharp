# Finbourne.Sdk.Lusid.Model.PropertyValueIn

A criterion that checks whether a Property Value is equal to one of the given string values
> **Inherits from:** [MatchCriterion](MatchCriterion.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PropertyKey** | **string** | Required | The property key whose value will form the left-hand side of the operation |
| **Value** | **List&lt;string&gt;** | Required | The value to be compared against |
| **CriterionType** | **string** | Required | The available values are: PropertyValueEquals, PropertyValueIn, SubHoldingKeyValueEquals Default: `CriterionTypeEnum.PropertyValueIn` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PropertyValueIn(
    propertyKey: "...",  // required — The property key whose value will form the left-hand side of the operation
    value: ,  // required — The value to be compared against
    criterionType: "..."  // required — The available values are: PropertyValueEquals, PropertyValueIn, SubHoldingKeyValueEquals
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PropertyValueIn>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

