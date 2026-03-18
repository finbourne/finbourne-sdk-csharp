# Finbourne.Sdk.Lusid.Model.ShareClassBreakdown

The Valuation Point Data for a Share Class on a specified date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BackOut** | [Dictionary&lt;string, ShareClassAmount&gt;](ShareClassAmount.md) | Required | Bucket of detail for the Valuation Point where data points have been &#39;backed out&#39;. |
| **Dealing** | [ShareClassDealingBreakdown](ShareClassDealingBreakdown.md) | Required | *No description available.* |
| **PnL** | [ShareClassPnlBreakdown](ShareClassPnlBreakdown.md) | Required | *No description available.* |
| **Gav** | [ShareClassAmount](ShareClassAmount.md) | Required | *No description available.* |
| **Fees** | [Dictionary&lt;string, FeeAccrual&gt;](FeeAccrual.md) | Required | Bucket of detail for any &#39;Fees&#39; that have been charged in the selected period. |
| **Nav** | [ShareClassAmount](ShareClassAmount.md) | Required | *No description available.* |
| **Unitisation** | [UnitisationData](UnitisationData.md) | Optional | *No description available.* |
| **Miscellaneous** | [Dictionary&lt;string, ShareClassAmount&gt;](ShareClassAmount.md) | Optional | Not used directly by the LUSID engines but serves as a holding area for any custom derived data points that may be useful in, for example, fee calculations). |
| **ShareClassToFundFxRate** | **decimal** | Required | The fx rate from the Share Class currency to the fund currency at this valuation point. |
| **CapitalRatio** | **decimal** | Required | The proportion of the fund&#39;s adjusted beginning equity (ie: the sum of the previous NAV and the net dealing) that is invested in the share class. |
| **PreviousShareClassBreakdown** | [PreviousShareClassBreakdown](PreviousShareClassBreakdown.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ShareClassBreakdown(
    backOut: new ShareClassAmount(...),  // required — Bucket of detail for the Valuation Point where data points have been &#39;backed out&#39;.
    dealing: new ShareClassDealingBreakdown(...),  // required
    pnL: new ShareClassPnlBreakdown(...),  // required
    gav: new ShareClassAmount(...),  // required
    fees: new FeeAccrual(...),  // required — Bucket of detail for any &#39;Fees&#39; that have been charged in the selected period.
    nav: new ShareClassAmount(...),  // required
    unitisation: new UnitisationData(...),  // optional
    miscellaneous: new ShareClassAmount(...),  // optional — Not used directly by the LUSID engines but serves as a holding area for any custom derived data points that may be useful in, for example, fee calculations).
    shareClassToFundFxRate: 0.0d,  // required — The fx rate from the Share Class currency to the fund currency at this valuation point.
    capitalRatio: 0.0d,  // required — The proportion of the fund&#39;s adjusted beginning equity (ie: the sum of the previous NAV and the net dealing) that is invested in the share class.
    previousShareClassBreakdown: new PreviousShareClassBreakdown(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ShareClassBreakdown>(json);
```


## Related Models

- [ShareClassAmount](ShareClassAmount.md) — used in `BackOut`
- [ShareClassDealingBreakdown](ShareClassDealingBreakdown.md)
- [ShareClassPnlBreakdown](ShareClassPnlBreakdown.md)
- [ShareClassAmount](ShareClassAmount.md)
- [FeeAccrual](FeeAccrual.md) — used in `Fees`
- [ShareClassAmount](ShareClassAmount.md)
- [UnitisationData](UnitisationData.md)
- [ShareClassAmount](ShareClassAmount.md) — used in `Miscellaneous`
- [PreviousShareClassBreakdown](PreviousShareClassBreakdown.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

