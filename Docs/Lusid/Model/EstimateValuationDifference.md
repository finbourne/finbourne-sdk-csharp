# Finbourne.Sdk.Lusid.Model.EstimateValuationDifference

How far apart the estimate-price and last-official-price valuations of the net dealing flow are.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Amount** | **decimal** | Required | The estimate-price net cashflow less the last-official-price net cashflow, in the fund currency. Negative when the last official price values the net flow higher. |
| **PctOfNav** | **decimal?** | Optional | The amount as a percentage of the fund&#39;s NAV at the previous valuation point. Absent when there is no previous NAV. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EstimateValuationDifference(
    amount: 0.0d,  // required — The estimate-price net cashflow less the last-official-price net cashflow, in the fund currency. Negative when the last official price values the net flow higher.
    pctOfNav: 0.0d  // optional — The amount as a percentage of the fund&#39;s NAV at the previous valuation point. Absent when there is no previous NAV.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EstimateValuationDifference>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

