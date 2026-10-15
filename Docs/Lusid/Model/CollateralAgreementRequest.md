# Finbourne.Sdk.Lusid.Model.CollateralAgreementRequest

The request used to create a Collateral Agreement.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the Collateral Agreement. |
| **CounterpartyId** | [CounterpartyIdentifier](CounterpartyIdentifier.md) | Required | *No description available.* |
| **ApplicabilityFilter** | **string** | Required | A filter selecting the portfolios and trades the agreement covers. Checked for structure only when the agreement is stored. |
| **BaseCurrency** | **string** | Required | The currency margin is calculated and called in. Filterable. |
| **CutLabel** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The cut label naming the market data that margin is valued at. |
| **RecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **MinimumTransferAmount** | **decimal?** | Optional | The smallest margin movement that is called. Optional. |
| **Rounding** | [MarginRounding](MarginRounding.md) | Required | *No description available.* |
| **SettlementLag** | [MarginSettlementLag](MarginSettlementLag.md) | Required | *No description available.* |
| **MatchTolerance** | **decimal?** | Optional | The tolerance within which our margin figure and the counterparty&#39;s are considered to match. Optional. |
| **VariationMargin** | [List&lt;MarginItem&gt;](MarginItem.md) | Optional | The variation margin arrangements under the agreement. |
| **InitialMargin** | [List&lt;MarginItem&gt;](MarginItem.md) | Optional | The initial margin arrangements under the agreement. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties to decorate onto the Collateral Agreement. Filterable. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effective datetime from which the Collateral Agreement applies. Defaults to the beginning of time if not specified, so that the agreement is visible at every effective datetime. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CollateralAgreementRequest(
    code: "...",  // required — The code of the Collateral Agreement.
    counterpartyId: new CounterpartyIdentifier(...),  // required
    applicabilityFilter: "...",  // required — A filter selecting the portfolios and trades the agreement covers. Checked for structure only when the agreement is stored.
    baseCurrency: "...",  // required — The currency margin is calculated and called in. Filterable.
    cutLabel: new DateTimeOrCutLabel(...),  // required — The cut label naming the market data that margin is valued at.
    recipeId: new ResourceId(...),  // required
    minimumTransferAmount: 0.0d,  // optional — The smallest margin movement that is called. Optional.
    rounding: new MarginRounding(...),  // required
    settlementLag: new MarginSettlementLag(...),  // required
    matchTolerance: 0.0d,  // optional — The tolerance within which our margin figure and the counterparty&#39;s are considered to match. Optional.
    variationMargin: new List<MarginItem>(),  // optional — The variation margin arrangements under the agreement.
    initialMargin: new List<MarginItem>(),  // optional — The initial margin arrangements under the agreement.
    properties: new Property(...),  // optional — A set of properties to decorate onto the Collateral Agreement. Filterable.
    effectiveAt: DateTimeOffset.Now  // optional — The effective datetime from which the Collateral Agreement applies. Defaults to the beginning of time if not specified, so that the agreement is visible at every effective datetime.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CollateralAgreementRequest>(json);
```

- [CounterpartyIdentifier](CounterpartyIdentifier.md)
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `CutLabel`
- [ResourceId](ResourceId.md)
- [MarginRounding](MarginRounding.md)
- [MarginSettlementLag](MarginSettlementLag.md)
- [MarginItem](MarginItem.md) — used in `VariationMargin`
- [MarginItem](MarginItem.md) — used in `InitialMargin`
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

