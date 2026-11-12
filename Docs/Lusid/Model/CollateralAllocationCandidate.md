# Finbourne.Sdk.Lusid.Model.CollateralAllocationCandidate

One holding the allocation considered for a margin call, with its figures as far as they could be computed and  either its rank or the constraint that excluded it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentId** | **string** | Required | The LUSID instrument identifier of the asset, or CCY_ and the currency code for cash. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The instrument identifiers a transaction for the line is booked against. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **CustodianAccount** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **AssetKind** | **string** | Required | Cash or Security. |
| **Currency** | **string** | Optional | The currency the asset is denominated in, when known. |
| **UnitsFree** | **decimal** | Required | Units not in a margin account and not promised to an earlier call of the run. |
| **LotSize** | **decimal** | Required | The smallest number of units the asset is delivered in. |
| **Price** | **decimal?** | Optional | The market value per unit in the base currency, before any haircut. Null when the asset could not be priced. |
| **EligibilitySeq** | **int?** | Optional | The one-based position of the schedule row that admits the asset. Null when no row does. |
| **ValuationPercentage** | **decimal?** | Optional | The fraction of market value the schedule row counts as collateral. |
| **FxHaircut** | **decimal?** | Optional | The further fraction deducted because the asset is not in the base currency. Zero when it is. |
| **EffectiveValuePerUnit** | **decimal?** | Optional | Price times the valuation percentage, less the FX haircut: what one unit counts for as collateral. |
| **OpportunityRate** | **decimal?** | Optional | The annual rate the fund gives up by locking the asset up: funding less the agreement&#39;s cash interest for cash, the lending fee it would otherwise earn for a security. |
| **CostPerUnitOfValue** | **decimal?** | Optional | The ranking key: the annual cost of one unit of collateral value from this asset. |
| **ConcentrationCap** | **decimal?** | Optional | The collateral value the schedule&#39;s concentration limit still allows from the asset&#39;s group. Null when the row sets no limit. |
| **SettlementDate** | **DateTimeOffset?** | Optional | When the movement would settle under the agreement&#39;s settlement lag, counting weekdays. |
| **Rank** | **int?** | Optional | The asset&#39;s position in the ranking, cheapest first. Null when excluded. |
| **ExclusionReason** | **string** | Optional | The constraint the asset failed, when it did. One of NotEligible, NoFreeUnits, MissingPrice, MissingRate, MissesDeadline, BelowMinimumLot or ConcentrationExhausted. Null when it passed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CollateralAllocationCandidate(
    instrumentId: "...",  // required — The LUSID instrument identifier of the asset, or CCY_ and the currency code for cash.
    instrumentIdentifiers: ,  // required — The instrument identifiers a transaction for the line is booked against.
    portfolioId: new ResourceId(...),  // required
    custodianAccount: new ResourceId(...),  // optional
    assetKind: "...",  // required — Cash or Security.
    currency: "...",  // optional — The currency the asset is denominated in, when known.
    unitsFree: 0.0d,  // required — Units not in a margin account and not promised to an earlier call of the run.
    lotSize: 0.0d,  // required — The smallest number of units the asset is delivered in.
    price: 0.0d,  // optional — The market value per unit in the base currency, before any haircut. Null when the asset could not be priced.
    eligibilitySeq: 0,  // optional — The one-based position of the schedule row that admits the asset. Null when no row does.
    valuationPercentage: 0.0d,  // optional — The fraction of market value the schedule row counts as collateral.
    fxHaircut: 0.0d,  // optional — The further fraction deducted because the asset is not in the base currency. Zero when it is.
    effectiveValuePerUnit: 0.0d,  // optional — Price times the valuation percentage, less the FX haircut: what one unit counts for as collateral.
    opportunityRate: 0.0d,  // optional — The annual rate the fund gives up by locking the asset up: funding less the agreement&#39;s cash interest for cash, the lending fee it would otherwise earn for a security.
    costPerUnitOfValue: 0.0d,  // optional — The ranking key: the annual cost of one unit of collateral value from this asset.
    concentrationCap: 0.0d,  // optional — The collateral value the schedule&#39;s concentration limit still allows from the asset&#39;s group. Null when the row sets no limit.
    settlementDate: DateTimeOffset.Now,  // optional — When the movement would settle under the agreement&#39;s settlement lag, counting weekdays.
    rank: 0,  // optional — The asset&#39;s position in the ranking, cheapest first. Null when excluded.
    exclusionReason: "..."  // optional — The constraint the asset failed, when it did. One of NotEligible, NoFreeUnits, MissingPrice, MissingRate, MissesDeadline, BelowMinimumLot or ConcentrationExhausted. Null when it passed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CollateralAllocationCandidate>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

