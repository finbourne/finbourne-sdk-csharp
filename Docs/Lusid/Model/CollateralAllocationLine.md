# Finbourne.Sdk.Lusid.Model.CollateralAllocationLine

One asset chosen for a margin call, with what a transaction moving it needs: the instrument, the portfolio and  account it leaves, the units, the price and the consideration. An override that fails a constraint is kept with  its exclusion reason and covers nothing.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentId** | **string** | Required | The LUSID instrument identifier of the asset, or CCY_ and the currency code for cash. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The instrument identifiers a transaction for the line is booked against. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **CustodianAccount** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Currency** | **string** | Optional | The currency the asset is denominated in, when known. |
| **Units** | **decimal** | Required | The units to move. |
| **Price** | **decimal?** | Optional | The market value per unit in the base currency, before any haircut. Null when the asset could not be priced. |
| **Consideration** | **decimal?** | Optional | Units times price in the base currency: what a transaction for the line settles. Null when the asset could not be priced. |
| **EffectiveValuePerUnit** | **decimal?** | Optional | Price times the valuation percentage, less the FX haircut: what one unit counts for as collateral. |
| **CollateralValue** | **decimal** | Required | The collateral value the line covers: units times the effective value per unit. |
| **CostPerUnitOfValue** | **decimal?** | Optional | The ranking key: the annual cost of one unit of collateral value from this asset. |
| **SettlementDate** | **DateTimeOffset?** | Optional | When the movement would settle under the agreement&#39;s settlement lag, counting weekdays. |
| **BoundBy** | **string** | Required | Which limit decided the units. One of RemainingRequirement, FreeUnits, ConcentrationCap, LotRounding or Override. |
| **ExclusionReason** | **string** | Optional | The constraint the asset failed, when it did. One of NotEligible, NoFreeUnits, MissingPrice, MissingRate, MissesDeadline, BelowMinimumLot or ConcentrationExhausted. Null when it passed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CollateralAllocationLine(
    instrumentId: "...",  // required — The LUSID instrument identifier of the asset, or CCY_ and the currency code for cash.
    instrumentIdentifiers: ,  // required — The instrument identifiers a transaction for the line is booked against.
    portfolioId: new ResourceId(...),  // required
    custodianAccount: new ResourceId(...),  // optional
    currency: "...",  // optional — The currency the asset is denominated in, when known.
    units: 0.0d,  // required — The units to move.
    price: 0.0d,  // optional — The market value per unit in the base currency, before any haircut. Null when the asset could not be priced.
    consideration: 0.0d,  // optional — Units times price in the base currency: what a transaction for the line settles. Null when the asset could not be priced.
    effectiveValuePerUnit: 0.0d,  // optional — Price times the valuation percentage, less the FX haircut: what one unit counts for as collateral.
    collateralValue: 0.0d,  // required — The collateral value the line covers: units times the effective value per unit.
    costPerUnitOfValue: 0.0d,  // optional — The ranking key: the annual cost of one unit of collateral value from this asset.
    settlementDate: DateTimeOffset.Now,  // optional — When the movement would settle under the agreement&#39;s settlement lag, counting weekdays.
    boundBy: "...",  // required — Which limit decided the units. One of RemainingRequirement, FreeUnits, ConcentrationCap, LotRounding or Override.
    exclusionReason: "..."  // optional — The constraint the asset failed, when it did. One of NotEligible, NoFreeUnits, MissingPrice, MissingRate, MissesDeadline, BelowMinimumLot or ConcentrationExhausted. Null when it passed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CollateralAllocationLine>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

