# Finbourne.Sdk.Lusid.Model.TaxCostRecord

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **TaxCostRecordCode** | **string** | Optional | The code of the Tax Cost Record, unique within the Fund. |
| **PortfolioScope** | **string** | Required | The scope of the portfolio the holding belongs to. |
| **PortfolioCode** | **string** | Required | The code of the portfolio the holding belongs to. |
| **InstrumentIdentifier** | **string** | Required | The LUSID instrument identifier (LUID) of the holding the tax cost applies to. |
| **NavTypeCode** | **string** | Optional | The code of the NAV type the tax cost applies to. Optional; omit for the fund&#39;s primary NAV type. |
| **TaxCost** | **decimal** | Required | The tax cost of the holding at the effective period end, in the fund&#39;s base currency. |
| **CarriedForwardAmount** | **decimal** | Required | The amount carried forward into the next tax period, in the fund&#39;s base currency. |
| **EffectivePeriodEnd** | **DateTimeOffset** | Required | The end date of the tax period the record applies to. |
| **SourceValuationPointId** | **string** | Optional | The identifier of the valuation point the record was derived from. Optional; omit for externally supplied records. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxCostRecord(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    taxCostRecordCode: "...",  // optional — The code of the Tax Cost Record, unique within the Fund.
    portfolioScope: "...",  // required — The scope of the portfolio the holding belongs to.
    portfolioCode: "...",  // required — The code of the portfolio the holding belongs to.
    instrumentIdentifier: "...",  // required — The LUSID instrument identifier (LUID) of the holding the tax cost applies to.
    navTypeCode: "...",  // optional — The code of the NAV type the tax cost applies to. Optional; omit for the fund&#39;s primary NAV type.
    taxCost: 0.0d,  // required — The tax cost of the holding at the effective period end, in the fund&#39;s base currency.
    carriedForwardAmount: 0.0d,  // required — The amount carried forward into the next tax period, in the fund&#39;s base currency.
    effectivePeriodEnd: DateTimeOffset.Now,  // required — The end date of the tax period the record applies to.
    sourceValuationPointId: "...",  // optional — The identifier of the valuation point the record was derived from. Optional; omit for externally supplied records.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxCostRecord>(json);
```

- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

