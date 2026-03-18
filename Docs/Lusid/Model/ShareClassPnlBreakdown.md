# Finbourne.Sdk.Lusid.Model.ShareClassPnlBreakdown

The breakdown of PnL for a Share Class on a specified date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ApportionedNonClassSpecificPnl** | [Dictionary&lt;string, ShareClassAmount&gt;](ShareClassAmount.md) | Required | Bucket of detail for PnL within the queried period not explicitly allocated to any share class but has been apportioned to the share class. |
| **ClassPnl** | [Dictionary&lt;string, ShareClassAmount&gt;](ShareClassAmount.md) | Required | Bucket of detail for PnL specific to the share class within the queried period. |
| **TotalPnl** | [Dictionary&lt;string, ShareClassAmount&gt;](ShareClassAmount.md) | Required | Bucket of detail for the sum of class PnL and PnL not specific to a class within the queried period. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ShareClassPnlBreakdown(
    apportionedNonClassSpecificPnl: new ShareClassAmount(...),  // required — Bucket of detail for PnL within the queried period not explicitly allocated to any share class but has been apportioned to the share class.
    classPnl: new ShareClassAmount(...),  // required — Bucket of detail for PnL specific to the share class within the queried period.
    totalPnl: new ShareClassAmount(...)  // required — Bucket of detail for the sum of class PnL and PnL not specific to a class within the queried period.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ShareClassPnlBreakdown>(json);
```


## Related Models

- [ShareClassAmount](ShareClassAmount.md) — used in `ApportionedNonClassSpecificPnl`
- [ShareClassAmount](ShareClassAmount.md) — used in `ClassPnl`
- [ShareClassAmount](ShareClassAmount.md) — used in `TotalPnl`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

