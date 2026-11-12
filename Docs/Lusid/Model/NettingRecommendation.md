# Finbourne.Sdk.Lusid.Model.NettingRecommendation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **string** | Required | The run the recommendation was made from. Filterable. |
| **SourceAgreementId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **SourceItem** | **string** | Required | The initial-margin item the trades would leave. Filterable. |
| **TargetAgreementId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TargetItem** | **string** | Required | The initial-margin item the trades would join. Filterable. |
| **Transfer** | **string** | Required | How the trades would get there: Redesignation when both agreements face one counterparty, Novation otherwise. Filterable. |
| **InstrumentType** | **string** | Optional | LUSID&#39;s type for the instruments in the cluster. Filterable. |
| **Currency** | **string** | Optional | The currency the cluster&#39;s trades are denominated in. Filterable. |
| **MaturityBucket** | **string** | Optional | The residual-maturity bucket the cluster&#39;s trades fall in on the run date; empty for instruments without a maturity. Filterable. |
| **Trades** | [List&lt;TradeReference&gt;](TradeReference.md) | Required | The holdings that would move. |
| **SavingPerDay** | **decimal** | Required | What we would no longer fund each day across both sets, in the sets&#39; base currency. Filterable. |
| **OneOffCost** | **decimal** | Required | The novation cost when the transfer is one; zero for a re-designation. Filterable. |
| **PaybackDays** | **decimal** | Required | How many days of saving cover the one-off cost. Filterable. |
| **InitialMarginChange** | **decimal** | Required | The sum over both sets of what we would post after the move less what we post today. Filterable. |
| **Source** | [InitialMarginChange](InitialMarginChange.md) | Required | *No description available.* |
| **Target** | [InitialMarginChange](InitialMarginChange.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new NettingRecommendation(
    runId: "...",  // required — The run the recommendation was made from. Filterable.
    sourceAgreementId: new ResourceId(...),  // required
    sourceItem: "...",  // required — The initial-margin item the trades would leave. Filterable.
    targetAgreementId: new ResourceId(...),  // required
    targetItem: "...",  // required — The initial-margin item the trades would join. Filterable.
    transfer: "...",  // required — How the trades would get there: Redesignation when both agreements face one counterparty, Novation otherwise. Filterable.
    instrumentType: "...",  // optional — LUSID&#39;s type for the instruments in the cluster. Filterable.
    currency: "...",  // optional — The currency the cluster&#39;s trades are denominated in. Filterable.
    maturityBucket: "...",  // optional — The residual-maturity bucket the cluster&#39;s trades fall in on the run date; empty for instruments without a maturity. Filterable.
    trades: new List<TradeReference>(),  // required — The holdings that would move.
    savingPerDay: 0.0d,  // required — What we would no longer fund each day across both sets, in the sets&#39; base currency. Filterable.
    oneOffCost: 0.0d,  // required — The novation cost when the transfer is one; zero for a re-designation. Filterable.
    paybackDays: 0.0d,  // required — How many days of saving cover the one-off cost. Filterable.
    initialMarginChange: 0.0d,  // required — The sum over both sets of what we would post after the move less what we post today. Filterable.
    source: new InitialMarginChange(...),  // required
    target: new InitialMarginChange(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NettingRecommendation>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [TradeReference](TradeReference.md) — used in `Trades`
- [InitialMarginChange](InitialMarginChange.md)
- [InitialMarginChange](InitialMarginChange.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

