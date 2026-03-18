# Finbourne.Sdk.Lusid.Model.MatchCriterion

A condition to be evaluated.  Each supported CriterionType has a corresponding schema.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CriterionType** | **string** | Required | The available values are: PropertyValueEquals, PropertyValueIn, SubHoldingKeyValueEquals |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MatchCriterion(
    criterionType: "..."  // required — The available values are: PropertyValueEquals, PropertyValueIn, SubHoldingKeyValueEquals
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MatchCriterion>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

