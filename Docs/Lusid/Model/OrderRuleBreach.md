# Finbourne.Sdk.Lusid.Model.OrderRuleBreach

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BreachTaskId** | **string** | Required | Uniquely identifies this historical order breach workflow task. |
| **ComplianceState** | **string** | Required | The compliance state of this order breach. Available values: Pending, Failed, Passed, ManuallyApproved, PartiallyOverridden, Warning. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderRuleBreach(
    breachTaskId: "...",  // required — Uniquely identifies this historical order breach workflow task.
    complianceState: "..."  // required — The compliance state of this order breach. Available values: Pending, Failed, Passed, ManuallyApproved, PartiallyOverridden, Warning.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderRuleBreach>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

