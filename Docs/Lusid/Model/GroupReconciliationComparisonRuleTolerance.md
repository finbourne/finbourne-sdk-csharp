# Finbourne.Sdk.Lusid.Model.GroupReconciliationComparisonRuleTolerance

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of tolerance to allow. \&quot;Relative\&quot; | \&quot;Absolute\&quot; |
| **Value** | **decimal** | Required | The decimal value of how much tolerance to allow when comparing in relative (i.e percentage) or absolute terms depending on the ToleranceType specified |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationComparisonRuleTolerance(
    type: "...",  // required — The type of tolerance to allow. \&quot;Relative\&quot; | \&quot;Absolute\&quot;
    value: 0.0d  // required — The decimal value of how much tolerance to allow when comparing in relative (i.e percentage) or absolute terms depending on the ToleranceType specified
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationComparisonRuleTolerance>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

