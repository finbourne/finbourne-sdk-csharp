# Finbourne.Sdk.Lusid.Model.LoanFacilityTaxLotState

Facility-level state for a single tax lot. These values live on the facility holding rather than on any  contract holding, and are keyed on the tax lot alone - a lot holding balances on several contracts still  has one cost and one facility accrual.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaxLotId** | **string** | Required | The tax lot being set, identified by the transaction id of the trade that opened it. |
| **Cost** | **decimal?** | Optional | The cost of this tax lot in the instrument&#39;s domestic currency, which for a loan facility is the  facility currency. Maps to Holding/Cost/Dom.                Stated rather than derived because loan facility cost is not units multiplied by price - it is the  funded balance at price plus the unfunded balance at price less par. A migrated lot whose real cost  came from several historical trades at different prices cannot be expressed by choosing one price on  the trade that opens it. Omit it to keep whatever cost that trade established. |
| **CostInPortfolioCcy** | **decimal?** | Optional | The cost of this tax lot in the portfolio currency. Maps to Holding/Cost/Pfolio, and is what makes  unrealised PnL exact across a currency boundary. Equals Cost multiplied by PortfolioFxRate. |
| **PortfolioFxRate** | **decimal?** | Optional | The FX rate from the facility currency to the portfolio currency at the time of the original trade.  One when the two currencies are the same. |
| **FacilityAccruedInterest** | **decimal?** | Optional | Accrued interest on the unfunded portion of the facility for this tax lot - the commitment fee. The  facility&#39;s own accrual, distinct from the accruals held against each contract, and already in the  facility currency. The two are summed to give the accrued interest reported against the holding.                Omit it and the lot&#39;s accrual is left as it is, so a migrated lot accrues from its own trade date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LoanFacilityTaxLotState(
    taxLotId: "...",  // required — The tax lot being set, identified by the transaction id of the trade that opened it.
    cost: 0.0d,  // optional — The cost of this tax lot in the instrument&#39;s domestic currency, which for a loan facility is the  facility currency. Maps to Holding/Cost/Dom.                Stated rather than derived because loan facility cost is not units multiplied by price - it is the  funded balance at price plus the unfunded balance at price less par. A migrated lot whose real cost  came from several historical trades at different prices cannot be expressed by choosing one price on  the trade that opens it. Omit it to keep whatever cost that trade established.
    costInPortfolioCcy: 0.0d,  // optional — The cost of this tax lot in the portfolio currency. Maps to Holding/Cost/Pfolio, and is what makes  unrealised PnL exact across a currency boundary. Equals Cost multiplied by PortfolioFxRate.
    portfolioFxRate: 0.0d,  // optional — The FX rate from the facility currency to the portfolio currency at the time of the original trade.  One when the two currencies are the same.
    facilityAccruedInterest: 0.0d  // optional — Accrued interest on the unfunded portion of the facility for this tax lot - the commitment fee. The  facility&#39;s own accrual, distinct from the accruals held against each contract, and already in the  facility currency. The two are summed to give the accrued interest reported against the holding.                Omit it and the lot&#39;s accrual is left as it is, so a migrated lot accrues from its own trade date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LoanFacilityTaxLotState>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

