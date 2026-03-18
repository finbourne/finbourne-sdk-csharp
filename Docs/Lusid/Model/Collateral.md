# Finbourne.Sdk.Lusid.Model.Collateral

Representation of the collateral of a repurchase agreement, along with related details of the agreement.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BuyerReceivesCashflows** | **bool** | Required | Does the buyer of the FlexibleRepo receive the cashflows from any collateral instruments, or do they get paid to the seller. |
| **BuyerReceivesCorporateActionPayments** | **bool** | Required | Does the buyer of the FlexibleRepo receive any dividend or cash payments as the result of a corporate action  on any of the collateral instruments, or are these amounts paid to the seller.  Referred to as \&quot;manufactured payments\&quot; in the UK, and valid only under a repo with GMRA in Europe |
| **CollateralInstruments** | [List&lt;CollateralInstrument&gt;](CollateralInstrument.md) | Optional | List of any collateral instruments. |
| **CollateralValue** | **decimal?** | Optional | Total value of the collateral before any margin or haircut applied.  Can be provided instead of PurchasePrice, so that PurchasePrice can be inferred from the CollateralValue and one of  Haircut or Margin. |
| **DeferManufacturedPayments** | **bool** | Optional | Indicates whether manufactured collateral payments are capitalised (i.e. deferred). Capitalised payments will  be deferred to the maturity date of the repo and if applicable interest will be accrued at the repo rate.  Defaults to false. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Collateral(
    buyerReceivesCashflows: true,  // required — Does the buyer of the FlexibleRepo receive the cashflows from any collateral instruments, or do they get paid to the seller.
    buyerReceivesCorporateActionPayments: true,  // required — Does the buyer of the FlexibleRepo receive any dividend or cash payments as the result of a corporate action  on any of the collateral instruments, or are these amounts paid to the seller.  Referred to as \&quot;manufactured payments\&quot; in the UK, and valid only under a repo with GMRA in Europe
    collateralInstruments: new List<CollateralInstrument>(),  // optional — List of any collateral instruments.
    collateralValue: 0.0d,  // optional — Total value of the collateral before any margin or haircut applied.  Can be provided instead of PurchasePrice, so that PurchasePrice can be inferred from the CollateralValue and one of  Haircut or Margin.
    deferManufacturedPayments: true  // optional — Indicates whether manufactured collateral payments are capitalised (i.e. deferred). Capitalised payments will  be deferred to the maturity date of the repo and if applicable interest will be accrued at the repo rate.  Defaults to false.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Collateral>(json);
```

- [CollateralInstrument](CollateralInstrument.md) — used in `CollateralInstruments`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

