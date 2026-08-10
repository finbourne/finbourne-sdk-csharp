# Finbourne.Sdk.Lusid.Model.CashFlowHaircutTermPoint

A point on a cashflow haircut term structure: the haircut rate applying at a given tenor from  the valuation date. Rates are linearly interpolated on time-to-payment between points and  extrapolated flat beyond either end of the term structure.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Tenor** | **string** | Required | The tenor from the valuation date at which the rate applies, e.g. &#39;6M&#39; or &#39;5Y&#39;. |
| **Rate** | **decimal** | Required | The haircut rate applying at the tenor, as a fraction in the range [0, 1]. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CashFlowHaircutTermPoint(
    tenor: "...",  // required — The tenor from the valuation date at which the rate applies, e.g. &#39;6M&#39; or &#39;5Y&#39;.
    rate: 0.0d  // required — The haircut rate applying at the tenor, as a fraction in the range [0, 1].
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CashFlowHaircutTermPoint>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

