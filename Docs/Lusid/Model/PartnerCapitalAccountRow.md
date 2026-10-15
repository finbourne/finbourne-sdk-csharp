# Finbourne.Sdk.Lusid.Model.PartnerCapitalAccountRow

One row of the capital account statement with its quarter-, year- and inception-to-date amounts.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RowType** | **string** | Required | The row type: BeginningCapital, Contributions, Distributions, TransfersIn, TransfersOut, NetOperatingIncome, ManagementFeesGross, ManagementFeeOffsets, RealisedGainLoss, UnrealisedGainLoss, CarriedInterest or EndingCapital. |
| **Qtd** | **decimal** | Required | The quarter-to-date amount for the row. |
| **Ytd** | **decimal** | Required | The year-to-date amount for the row. |
| **Itd** | **decimal** | Required | The inception-to-date amount for the row. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerCapitalAccountRow(
    rowType: "...",  // required — The row type: BeginningCapital, Contributions, Distributions, TransfersIn, TransfersOut, NetOperatingIncome, ManagementFeesGross, ManagementFeeOffsets, RealisedGainLoss, UnrealisedGainLoss, CarriedInterest or EndingCapital.
    qtd: 0.0d,  // required — The quarter-to-date amount for the row.
    ytd: 0.0d,  // required — The year-to-date amount for the row.
    itd: 0.0d  // required — The inception-to-date amount for the row.
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



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

