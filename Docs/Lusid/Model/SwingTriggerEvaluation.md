# Finbourne.Sdk.Lusid.Model.SwingTriggerEvaluation

How a Market swing trigger was evaluated at a valuation point.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Fired** | **bool** | Required | Whether the net cashflow was in the trigger&#39;s direction and above its threshold. |
| **Threshold** | **decimal** | Required | The trigger&#39;s threshold. |
| **Metric** | **string** | Required | What the threshold measured: NetCashflowAbsolute or NetCashflowPctOfNav. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SwingTriggerEvaluation(
    fired: true,  // required — Whether the net cashflow was in the trigger&#39;s direction and above its threshold.
    threshold: 0.0d,  // required — The trigger&#39;s threshold.
    metric: "..."  // required — What the threshold measured: NetCashflowAbsolute or NetCashflowPctOfNav.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SwingTriggerEvaluation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

