# Finbourne.Sdk.Lusid.Model.FundValuationPointData

The Valuation Point Data for a Fund on a specified date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BackOut** | [Dictionary&lt;string, FundAmount&gt;](FundAmount.md) | Required | Bucket of detail for the Valuation Point where data points have been &#39;backed out&#39;. |
| **Dealing** | [Dictionary&lt;string, FundAmount&gt;](FundAmount.md) | Required | Bucket of detail for any &#39;Dealing&#39; that has occured inside the queried period. |
| **PnL** | [FundPnlBreakdown](FundPnlBreakdown.md) | Required | *No description available.* |
| **Gav** | **decimal** | Required | The Gross Asset Value of the Fund or Share Class at the Valuation Point. This is effectively a summation of all Trial balance entries linked to accounts of types &#39;Asset&#39; and &#39;Liabilities&#39;. |
| **Fees** | [Dictionary&lt;string, FeeAccrual&gt;](FeeAccrual.md) | Required | Bucket of detail for any &#39;Fees&#39; that have been charged in the selected period. |
| **Nav** | **decimal** | Required | The Net Asset Value of the Fund or Share Class at the Valuation Point. This represents the GAV with any fees applied in the period. |
| **Miscellaneous** | [Dictionary&lt;string, FundAmount&gt;](FundAmount.md) | Optional | Not used directly by the LUSID engines but serves as a holding area for any custom derived data points that may be useful in, for example, fee calculations). |
| **PreviousValuationPointData** | [PreviousFundValuationPointData](PreviousFundValuationPointData.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundValuationPointData(
    backOut: new FundAmount(...),  // required — Bucket of detail for the Valuation Point where data points have been &#39;backed out&#39;.
    dealing: new FundAmount(...),  // required — Bucket of detail for any &#39;Dealing&#39; that has occured inside the queried period.
    pnL: new FundPnlBreakdown(...),  // required
    gav: 0.0d,  // required — The Gross Asset Value of the Fund or Share Class at the Valuation Point. This is effectively a summation of all Trial balance entries linked to accounts of types &#39;Asset&#39; and &#39;Liabilities&#39;.
    fees: new FeeAccrual(...),  // required — Bucket of detail for any &#39;Fees&#39; that have been charged in the selected period.
    nav: 0.0d,  // required — The Net Asset Value of the Fund or Share Class at the Valuation Point. This represents the GAV with any fees applied in the period.
    miscellaneous: new FundAmount(...),  // optional — Not used directly by the LUSID engines but serves as a holding area for any custom derived data points that may be useful in, for example, fee calculations).
    previousValuationPointData: new PreviousFundValuationPointData(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundValuationPointData>(json);
```


## Related Models

- [FundAmount](FundAmount.md) — used in `BackOut`
- [FundAmount](FundAmount.md) — used in `Dealing`
- [FundPnlBreakdown](FundPnlBreakdown.md)
- [FeeAccrual](FeeAccrual.md) — used in `Fees`
- [FundAmount](FundAmount.md) — used in `Miscellaneous`
- [PreviousFundValuationPointData](PreviousFundValuationPointData.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

