# Finbourne.Sdk.Lusid.Model.OrderRuleBreach

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BreachTaskId** | **string** | Required | Uniquely identifies this historical order breach workflow task. |
| **ComplianceState** | **string** | Required | The compliance state of this order breach. Possible values are &#39;Pending&#39;, &#39;Failed&#39;, &#39;Manually approved&#39;, &#39;Passed&#39; and &#39;Warning&#39;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderRuleBreach(
    breachTaskId: "...",  // required — Uniquely identifies this historical order breach workflow task.
    complianceState: "..."  // required — The compliance state of this order breach. Possible values are &#39;Pending&#39;, &#39;Failed&#39;, &#39;Manually approved&#39;, &#39;Passed&#39; and &#39;Warning&#39;.
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

