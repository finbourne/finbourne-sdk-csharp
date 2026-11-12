# Finbourne.Sdk.Lusid.Model.DealingFlowValuation

The transfer agency's dealing flows with unit-denominated orders valued at one unit price, and the swing outcome that net flow leads the methodology to.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NetCashflow** | **decimal** | Required | The inflows less the outflows at this unit price, in the fund currency. |
| **NetCashflowPctOfNav** | **decimal?** | Optional | The net cashflow as a percentage of the fund&#39;s NAV at the previous valuation point. Absent when there is no previous NAV. |
| **GrossInflow** | **decimal** | Required | The sum of the inflows at this unit price, in the fund currency. Zero or more. |
| **GrossOutflow** | **decimal** | Required | The sum of the outflows at this unit price, in the fund currency, as a magnitude. Zero or more. |
| **Outcome** | [EstimateValuationOutcome](EstimateValuationOutcome.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DealingFlowValuation(
    netCashflow: 0.0d,  // required — The inflows less the outflows at this unit price, in the fund currency.
    netCashflowPctOfNav: 0.0d,  // optional — The net cashflow as a percentage of the fund&#39;s NAV at the previous valuation point. Absent when there is no previous NAV.
    grossInflow: 0.0d,  // required — The sum of the inflows at this unit price, in the fund currency. Zero or more.
    grossOutflow: 0.0d,  // required — The sum of the outflows at this unit price, in the fund currency, as a magnitude. Zero or more.
    outcome: new EstimateValuationOutcome(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DealingFlowValuation>(json);
```

- [EstimateValuationOutcome](EstimateValuationOutcome.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

