# Finbourne.Sdk.Lusid.Model.SwingTrigger

When a Market swing fires in one direction: the net cashflow measure and the size it must exceed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | What the threshold measures: NetCashflowAbsolute, the size of the net cashflow in the fund currency, or NetCashflowPctOfNav, the net cashflow as a percentage of the previous valuation point&#39;s NAV. A NetCashflowPctOfNav trigger does not fire when there is no previous NAV. Available values: NetCashflowAbsolute, NetCashflowPctOfNav. |
| **Threshold** | **decimal** | Required | The size of net cashflow, as a magnitude, the flow must be above for the trigger to fire. Above zero. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SwingTrigger(
    type: "...",  // required — What the threshold measures: NetCashflowAbsolute, the size of the net cashflow in the fund currency, or NetCashflowPctOfNav, the net cashflow as a percentage of the previous valuation point&#39;s NAV. A NetCashflowPctOfNav trigger does not fire when there is no previous NAV. Available values: NetCashflowAbsolute, NetCashflowPctOfNav.
    threshold: 0.0d  // required — The size of net cashflow, as a magnitude, the flow must be above for the trigger to fire. Above zero.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SwingTrigger>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

