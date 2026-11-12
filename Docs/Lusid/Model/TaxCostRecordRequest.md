# Finbourne.Sdk.Lusid.Model.TaxCostRecordRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioScope** | **string** | Required | The scope of the portfolio the holding belongs to. |
| **PortfolioCode** | **string** | Required | The code of the portfolio the holding belongs to. |
| **InstrumentIdentifier** | **string** | Required | The LUSID instrument identifier (LUID) of the holding the tax cost applies to. |
| **NavTypeCode** | **string** | Optional | The code of the NAV type the tax cost applies to. Optional; omit for the fund&#39;s primary NAV type. |
| **TaxCost** | **decimal** | Required | The tax cost of the holding at the effective period end, in the fund&#39;s base currency. |
| **CarriedForwardAmount** | **decimal** | Required | The amount carried forward into the next tax period, in the fund&#39;s base currency. |
| **EffectivePeriodEnd** | **DateTimeOffset** | Required | The end date of the tax period the record applies to. |
| **SourceValuationPointId** | **string** | Optional | The identifier of the valuation point the record was derived from. Optional; omit for externally supplied records. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxCostRecordRequest(
    portfolioScope: "...",  // required — The scope of the portfolio the holding belongs to.
    portfolioCode: "...",  // required — The code of the portfolio the holding belongs to.
    instrumentIdentifier: "...",  // required — The LUSID instrument identifier (LUID) of the holding the tax cost applies to.
    navTypeCode: "...",  // optional — The code of the NAV type the tax cost applies to. Optional; omit for the fund&#39;s primary NAV type.
    taxCost: 0.0d,  // required — The tax cost of the holding at the effective period end, in the fund&#39;s base currency.
    carriedForwardAmount: 0.0d,  // required — The amount carried forward into the next tax period, in the fund&#39;s base currency.
    effectivePeriodEnd: DateTimeOffset.Now,  // required — The end date of the tax period the record applies to.
    sourceValuationPointId: "..."  // optional — The identifier of the valuation point the record was derived from. Optional; omit for externally supplied records.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxCostRecordRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

