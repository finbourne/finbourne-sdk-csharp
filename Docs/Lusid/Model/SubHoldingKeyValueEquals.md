# Finbourne.Sdk.Lusid.Model.SubHoldingKeyValueEquals

A criterion that checks whether a SubHoldingKey Value is equal to the given string value
> **Inherits from:** [MatchCriterion](MatchCriterion.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SubHoldingKey** | **string** | Required | The sub holding key whose value will form the left-hand side of the operation |
| **Value** | **string** | Required | The value to be compared against |
| **CriterionType** | **string** | Required | The available values are: PropertyValueEquals, PropertyValueIn, SubHoldingKeyValueEquals Default: `CriterionTypeEnum.SubHoldingKeyValueEquals` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SubHoldingKeyValueEquals(
    subHoldingKey: "...",  // required — The sub holding key whose value will form the left-hand side of the operation
    value: "...",  // required — The value to be compared against
    criterionType: "..."  // required — The available values are: PropertyValueEquals, PropertyValueIn, SubHoldingKeyValueEquals
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SubHoldingKeyValueEquals>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

