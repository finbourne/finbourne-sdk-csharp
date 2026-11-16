# Finbourne.Sdk.Lusid.Model.PartnerCapitalAccountRow

One row of the capital account statement with its quarter-, year- and inception-to-date amounts.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RowType** | **string** | Required | The row type: BeginningCapital, Contributions, Distributions, TransfersIn, TransfersOut, NetOperatingIncome, ManagementFeesGross, ManagementFeeOffsets, RealisedGainLoss, UnrealisedGainLoss, CarriedInterest or EndingCapital. |
| **Qtd** | **decimal** | Required | The quarter-to-date amount for the row. |
| **Ytd** | **decimal** | Required | The year-to-date amount for the row. |
| **Itd** | **decimal** | Required | The inception-to-date amount for the row. |
| **Details** | [List&lt;PartnerCapitalAccountRowDetail&gt;](PartnerCapitalAccountRowDetail.md) | Optional | Labelled parts of the row&#39;s total, each already included in the row&#39;s columns. Tax withheld from a distribution on the partner&#39;s behalf is counted as distributed and shown here as its own entry against the distribution it was withheld on. Empty for a row with nothing to break out. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerCapitalAccountRow(
    rowType: "...",  // required — The row type: BeginningCapital, Contributions, Distributions, TransfersIn, TransfersOut, NetOperatingIncome, ManagementFeesGross, ManagementFeeOffsets, RealisedGainLoss, UnrealisedGainLoss, CarriedInterest or EndingCapital.
    qtd: 0.0d,  // required — The quarter-to-date amount for the row.
    ytd: 0.0d,  // required — The year-to-date amount for the row.
    itd: 0.0d,  // required — The inception-to-date amount for the row.
    details: new List<PartnerCapitalAccountRowDetail>()  // optional — Labelled parts of the row&#39;s total, each already included in the row&#39;s columns. Tax withheld from a distribution on the partner&#39;s behalf is counted as distributed and shown here as its own entry against the distribution it was withheld on. Empty for a row with nothing to break out.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerCapitalAccountRow>(json);
```

- [PartnerCapitalAccountRowDetail](PartnerCapitalAccountRowDetail.md) — used in `Details`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

