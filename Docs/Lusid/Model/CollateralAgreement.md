# Finbourne.Sdk.Lusid.Model.CollateralAgreement

A collateral agreement: who it covers, how exposure is valued, and the variation and initial margin  arrangements collateral is called and returned under.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **CounterpartyId** | [CounterpartyIdentifier](CounterpartyIdentifier.md) | Optional | *No description available.* |
| **ApplicabilityFilter** | **string** | Optional | A filter selecting the portfolios and trades the agreement covers. Checked for structure only when the agreement is stored. |
| **BaseCurrency** | **string** | Optional | The currency margin is calculated and called in. Filterable. |
| **CutLabel** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The cut label naming the market data that margin is valued at. |
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **MinimumTransferAmount** | **decimal?** | Optional | The smallest margin movement that is called. Optional. |
| **Rounding** | [MarginRounding](MarginRounding.md) | Optional | *No description available.* |
| **SettlementLag** | [MarginSettlementLag](MarginSettlementLag.md) | Optional | *No description available.* |
| **MatchTolerance** | **decimal?** | Optional | The tolerance within which our margin figure and the counterparty&#39;s are considered to match. Optional. |
| **Funding** | [CollateralFundingTerms](CollateralFundingTerms.md) | Optional | *No description available.* |
| **Optimisation** | [CollateralOptimisationTerms](CollateralOptimisationTerms.md) | Optional | *No description available.* |
| **VariationMargin** | [List&lt;MarginItem&gt;](MarginItem.md) | Optional | The variation margin arrangements under the agreement. |
| **InitialMargin** | [List&lt;MarginItem&gt;](MarginItem.md) | Optional | The initial margin arrangements under the agreement. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties to decorate onto the Collateral Agreement. Filterable. |
| **NotificationCutLabel** | **string** | Optional | The cut label giving the time of day by which collateral we deliver under a margin call must settle. Each run resolves it on the business date and records it as the call&#39;s deadline; the allocation excludes assets that cannot settle by it. Optional. |
| **ReturnNotificationCutLabel** | **string** | Optional | The cut label giving the time of day by which collateral the counterparty delivers, or returns to us, must settle. Recorded as the deadline of the calls they post under. Optional. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CollateralAgreement(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    counterpartyId: new CounterpartyIdentifier(...),  // optional
    applicabilityFilter: "...",  // optional — A filter selecting the portfolios and trades the agreement covers. Checked for structure only when the agreement is stored.
    baseCurrency: "...",  // optional — The currency margin is calculated and called in. Filterable.
    cutLabel: new DateTimeOrCutLabel(...),  // optional — The cut label naming the market data that margin is valued at.
    recipeId: new ResourceId(...),  // optional
    minimumTransferAmount: 0.0d,  // optional — The smallest margin movement that is called. Optional.
    rounding: new MarginRounding(...),  // optional
    settlementLag: new MarginSettlementLag(...),  // optional
    matchTolerance: 0.0d,  // optional — The tolerance within which our margin figure and the counterparty&#39;s are considered to match. Optional.
    funding: new CollateralFundingTerms(...),  // optional
    optimisation: new CollateralOptimisationTerms(...),  // optional
    variationMargin: new List<MarginItem>(),  // optional — The variation margin arrangements under the agreement.
    initialMargin: new List<MarginItem>(),  // optional — The initial margin arrangements under the agreement.
    varVersion: new ModelVersion(...),  // optional
    properties: new Property(...),  // optional — A set of properties to decorate onto the Collateral Agreement. Filterable.
    notificationCutLabel: "...",  // optional — The cut label giving the time of day by which collateral we deliver under a margin call must settle. Each run resolves it on the business date and records it as the call&#39;s deadline; the allocation excludes assets that cannot settle by it. Optional.
    returnNotificationCutLabel: "...",  // optional — The cut label giving the time of day by which collateral the counterparty delivers, or returns to us, must settle. Recorded as the deadline of the calls they post under. Optional.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CollateralAgreement>(json);
```

- [ResourceId](ResourceId.md)
- [CounterpartyIdentifier](CounterpartyIdentifier.md)
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `CutLabel`
- [ResourceId](ResourceId.md)
- [MarginRounding](MarginRounding.md)
- [MarginSettlementLag](MarginSettlementLag.md)
- [CollateralFundingTerms](CollateralFundingTerms.md)
- [CollateralOptimisationTerms](CollateralOptimisationTerms.md)
- [MarginItem](MarginItem.md) — used in `VariationMargin`
- [MarginItem](MarginItem.md) — used in `InitialMargin`
- [ModelVersion](ModelVersion.md)
- [Property](Property.md) — used in `Properties`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

