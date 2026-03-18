# Finbourne.Sdk.Lusid.Model.PortfolioHolding

A list of holdings.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentScope** | **string** | Optional | The scope in which the holding&#39;s instrument is in. |
| **InstrumentUid** | **string** | Required | The unique Lusid Instrument Id (LUID) of the instrument that the holding is in. |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The sub-holding properties which identify the holding. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The properties which have been requested to be decorated onto the holding. These will be from the &#39;Instrument&#39; or &#39;Holding&#39; domain. |
| **HoldingType** | **string** | Required | The code for the type of the holding e.g. P, B, C, R, F etc. |
| **Units** | **decimal** | Required | The total number of units of the holding. |
| **SettledUnits** | **decimal** | Required | The total number of settled units of the holding. |
| **Cost** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **CostPortfolioCcy** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **Transaction** | [Transaction](Transaction.md) | Optional | *No description available.* |
| **Currency** | **string** | Optional | The holding currency. |
| **HoldingTypeName** | **string** | Optional | The decoded type of the holding e.g. Position, Balance, CashCommitment, Receivable, ForwardFX etc. |
| **HoldingId** | **long?** | Optional | A single identifier for the holding within the portfolio. The holdingId is constructed from the LusidInstrumentId, sub-holding keys and currrency and is unique within the portfolio. |
| **NotionalCost** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **AmortisedCost** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **AmortisedCostPortfolioCcy** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **VariationMargin** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **VariationMarginPortfolioCcy** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **SettlementSchedule** | [List&lt;SettlementSchedule&gt;](SettlementSchedule.md) | Optional | Where no. of days ahead has been specified, future dated settlements will be captured here. |
| **CurrentFace** | **decimal?** | Optional | Current face value of the holding. |
| **CustodianAccountId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **UnsettledUnits** | **decimal** | Optional | The number of unsettled units for the holding. |
| **OverdueUnits** | **decimal** | Optional | The number of unsettled units for the holding that are beyond their contractual settlement date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioHolding(
    instrumentScope: "...",  // optional — The scope in which the holding&#39;s instrument is in.
    instrumentUid: "...",  // required — The unique Lusid Instrument Id (LUID) of the instrument that the holding is in.
    subHoldingKeys: new PerpetualProperty(...),  // optional — The sub-holding properties which identify the holding. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio.
    properties: new Property(...),  // optional — The properties which have been requested to be decorated onto the holding. These will be from the &#39;Instrument&#39; or &#39;Holding&#39; domain.
    holdingType: "...",  // required — The code for the type of the holding e.g. P, B, C, R, F etc.
    units: 0.0d,  // required — The total number of units of the holding.
    settledUnits: 0.0d,  // required — The total number of settled units of the holding.
    cost: new CurrencyAndAmount(...),  // required
    costPortfolioCcy: new CurrencyAndAmount(...),  // required
    transaction: new Transaction(...),  // optional
    currency: "...",  // optional — The holding currency.
    holdingTypeName: "...",  // optional — The decoded type of the holding e.g. Position, Balance, CashCommitment, Receivable, ForwardFX etc.
    holdingId: 0L,  // optional — A single identifier for the holding within the portfolio. The holdingId is constructed from the LusidInstrumentId, sub-holding keys and currrency and is unique within the portfolio.
    notionalCost: new CurrencyAndAmount(...),  // optional
    amortisedCost: new CurrencyAndAmount(...),  // optional
    amortisedCostPortfolioCcy: new CurrencyAndAmount(...),  // optional
    variationMargin: new CurrencyAndAmount(...),  // optional
    variationMarginPortfolioCcy: new CurrencyAndAmount(...),  // optional
    settlementSchedule: new List<SettlementSchedule>(),  // optional — Where no. of days ahead has been specified, future dated settlements will be captured here.
    currentFace: 0.0d,  // optional — Current face value of the holding.
    custodianAccountId: new ResourceId(...),  // optional
    unsettledUnits: 0.0d,  // optional — The number of unsettled units for the holding.
    overdueUnits: 0.0d  // optional — The number of unsettled units for the holding that are beyond their contractual settlement date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioHolding>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [Property](Property.md) — used in `Properties`
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [Transaction](Transaction.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [SettlementSchedule](SettlementSchedule.md) — used in `SettlementSchedule`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

