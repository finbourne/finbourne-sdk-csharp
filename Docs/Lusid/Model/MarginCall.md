# Finbourne.Sdk.Lusid.Model.MarginCall

A margin call a run produced under a collateral agreement: our figure, the counterparty's demand once recorded  and how they compare, and where the call is in its lifecycle.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The URI of this margin call. |
| **Id** | **string** | Required | The identifier of the call: the run id and the call&#39;s business key joined with &#39;/&#39;. |
| **RunId** | **string** | Required | The run that produced the call. Filterable. |
| **AgreementId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Counterparty** | [CounterpartyIdentifier](CounterpartyIdentifier.md) | Optional | *No description available.* |
| **Item** | **string** | Required | The margin item of the agreement the call is for. Filterable. |
| **MarginType** | **string** | Required | The type of margin called. Currently VariationMargin. Filterable. |
| **Method** | **string** | Optional | The calculation method of the margin item. |
| **Settlement** | **string** | Optional | Whether the item is settled or collateralised. |
| **Direction** | **string** | Required | Who posts: WePost, TheyPost or None when the exposure is flat. Filterable. |
| **Currency** | **string** | Required | The currency of the call, the agreement&#39;s base currency. Filterable. |
| **Required** | **decimal** | Required | The margin required under the agreement, signed as the call. |
| **Held** | **decimal** | Required | The collateral already held against the item, signed as the call. |
| **Call** | **decimal** | Required | Our figure for the amount to move: required less held. Filterable. |
| **MatchTolerance** | **decimal?** | Optional | The agreement&#39;s match tolerance captured on the call. |
| **CounterpartyDemand** | **decimal?** | Optional | The counterparty&#39;s figure for the call, once recorded. |
| **Difference** | **decimal?** | Optional | The counterparty&#39;s demand less our call, once recorded. |
| **MatchStatus** | **string** | Required | How the counterparty&#39;s demand compares to our call. One of Unmatched, Matched, WithinTolerance, Break or NotRequired. Filterable. |
| **DemandReceivedAt** | **DateTimeOffset?** | Optional | When the counterparty&#39;s demand was received. |
| **StatementReference** | **string** | Optional | A reference to the counterparty&#39;s statement, such as a Drive path. |
| **DemandNote** | **string** | Optional | A note recorded with the counterparty&#39;s demand. |
| **AgreedAmount** | **decimal?** | Optional | The amount agreed to move, once the call is accepted or disputed. |
| **DisputedAmount** | **decimal?** | Optional | The part of the counterparty&#39;s demand left in dispute. |
| **DisputeReason** | **string** | Optional | Why the call is disputed. |
| **DisputeOwner** | **string** | Optional | Who owns the dispute. |
| **State** | **string** | Required | Where the call is in its lifecycle. One of Calculated, Accepted or Disputed. Filterable. |
| **Deadline** | **DateTimeOffset?** | Optional | The time the call must be agreed by. Empty until agreements carry a notification time. |
| **Supersedes** | [MarginCallReference](MarginCallReference.md) | Optional | *No description available.* |
| **CarriedFrom** | [MarginCallReference](MarginCallReference.md) | Optional | *No description available.* |
| **CarriedDisputedAmount** | **decimal?** | Optional | The amount left in dispute on the carried call. Informational; not added to this call. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginCall(
    href: "...",  // optional — The URI of this margin call.
    id: "...",  // required — The identifier of the call: the run id and the call&#39;s business key joined with &#39;/&#39;.
    runId: "...",  // required — The run that produced the call. Filterable.
    agreementId: new ResourceId(...),  // required
    counterparty: new CounterpartyIdentifier(...),  // optional
    item: "...",  // required — The margin item of the agreement the call is for. Filterable.
    marginType: "...",  // required — The type of margin called. Currently VariationMargin. Filterable.
    method: "...",  // optional — The calculation method of the margin item.
    settlement: "...",  // optional — Whether the item is settled or collateralised.
    direction: "...",  // required — Who posts: WePost, TheyPost or None when the exposure is flat. Filterable.
    currency: "...",  // required — The currency of the call, the agreement&#39;s base currency. Filterable.
    required: 0.0d,  // required — The margin required under the agreement, signed as the call.
    held: 0.0d,  // required — The collateral already held against the item, signed as the call.
    call: 0.0d,  // required — Our figure for the amount to move: required less held. Filterable.
    matchTolerance: 0.0d,  // optional — The agreement&#39;s match tolerance captured on the call.
    counterpartyDemand: 0.0d,  // optional — The counterparty&#39;s figure for the call, once recorded.
    difference: 0.0d,  // optional — The counterparty&#39;s demand less our call, once recorded.
    matchStatus: "...",  // required — How the counterparty&#39;s demand compares to our call. One of Unmatched, Matched, WithinTolerance, Break or NotRequired. Filterable.
    demandReceivedAt: DateTimeOffset.Now,  // optional — When the counterparty&#39;s demand was received.
    statementReference: "...",  // optional — A reference to the counterparty&#39;s statement, such as a Drive path.
    demandNote: "...",  // optional — A note recorded with the counterparty&#39;s demand.
    agreedAmount: 0.0d,  // optional — The amount agreed to move, once the call is accepted or disputed.
    disputedAmount: 0.0d,  // optional — The part of the counterparty&#39;s demand left in dispute.
    disputeReason: "...",  // optional — Why the call is disputed.
    disputeOwner: "...",  // optional — Who owns the dispute.
    state: "...",  // required — Where the call is in its lifecycle. One of Calculated, Accepted or Disputed. Filterable.
    deadline: DateTimeOffset.Now,  // optional — The time the call must be agreed by. Empty until agreements carry a notification time.
    supersedes: new MarginCallReference(...),  // optional
    carriedFrom: new MarginCallReference(...),  // optional
    carriedDisputedAmount: 0.0d  // optional — The amount left in dispute on the carried call. Informational; not added to this call.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginCall>(json);
```

- [ResourceId](ResourceId.md)
- [CounterpartyIdentifier](CounterpartyIdentifier.md)
- [MarginCallReference](MarginCallReference.md)
- [MarginCallReference](MarginCallReference.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

