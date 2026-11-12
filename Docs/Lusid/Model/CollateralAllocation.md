# Finbourne.Sdk.Lusid.Model.CollateralAllocation

Which of our assets to move for a margin call and why: every holding considered, with its rank or the constraint  that excluded it, and the lines chosen cheapest first, each carrying what a transaction moving it needs. Amounts  are in the agreement's base currency.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **string** | Required | The run the call belongs to. |
| **CallId** | **string** | Required | The business key of the call within the run: agreement scope and code, item, margin type and direction joined with &#39;/&#39;. |
| **Direction** | **string** | Required | Whether the collateral is delivered to the counterparty or recalled from it. One of Deliver or Recall. |
| **InventorySource** | **string** | Required | Where the holdings were read from: RunStore for the proposal the run made, Live for a ranking against the holdings as they stand now. |
| **AsAt** | **DateTimeOffset** | Required | The asAt the holdings and terms were read at. |
| **AgreementId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Item** | **string** | Optional | The margin item of the call. |
| **Counterparty** | [CounterpartyIdentifier](CounterpartyIdentifier.md) | Optional | *No description available.* |
| **BusinessDate** | **DateTimeOffset?** | Optional | The business date of the call, which a transaction for a line trades on. |
| **Deadline** | **DateTimeOffset?** | Optional | When the movement must have settled under the agreement&#39;s cut label. Null when the agreement sets none. |
| **MarginAccount** | **string** | Optional | The code of the custodian account the item names for collateral we post, which a delivery moves assets into and a recall moves them out of. Null when the item names none. |
| **BaseCurrency** | **string** | Required | The agreement&#39;s base currency, which every amount is in. |
| **RequiredAmount** | **decimal** | Required | The collateral value to deliver, or for a recall the excess to take back. |
| **CoveredAmount** | **decimal** | Required | The collateral value of the lines chosen: below the requirement when the inventory ran out, above it when a lot could not be split. |
| **CarryPerDay** | **decimal** | Required | What the chosen lines cost the fund a day to leave locked up, in the base currency. |
| **AllCashCarryPerDay** | **decimal?** | Optional | What covering the whole call in base-currency cash would cost a day. Null when the cash rate is unavailable or for a recall. |
| **Candidates** | [List&lt;CollateralAllocationCandidate&gt;](CollateralAllocationCandidate.md) | Required | Every holding considered, ranked ones first by rank, then the excluded with the constraint that excluded them. |
| **Allocation** | [List&lt;CollateralAllocationLine&gt;](CollateralAllocationLine.md) | Required | The assets chosen, cheapest first, each with what a transaction moving it needs. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CollateralAllocation(
    runId: "...",  // required — The run the call belongs to.
    callId: "...",  // required — The business key of the call within the run: agreement scope and code, item, margin type and direction joined with &#39;/&#39;.
    direction: "...",  // required — Whether the collateral is delivered to the counterparty or recalled from it. One of Deliver or Recall.
    inventorySource: "...",  // required — Where the holdings were read from: RunStore for the proposal the run made, Live for a ranking against the holdings as they stand now.
    asAt: DateTimeOffset.Now,  // required — The asAt the holdings and terms were read at.
    agreementId: new ResourceId(...),  // optional
    item: "...",  // optional — The margin item of the call.
    counterparty: new CounterpartyIdentifier(...),  // optional
    businessDate: DateTimeOffset.Now,  // optional — The business date of the call, which a transaction for a line trades on.
    deadline: DateTimeOffset.Now,  // optional — When the movement must have settled under the agreement&#39;s cut label. Null when the agreement sets none.
    marginAccount: "...",  // optional — The code of the custodian account the item names for collateral we post, which a delivery moves assets into and a recall moves them out of. Null when the item names none.
    baseCurrency: "...",  // required — The agreement&#39;s base currency, which every amount is in.
    requiredAmount: 0.0d,  // required — The collateral value to deliver, or for a recall the excess to take back.
    coveredAmount: 0.0d,  // required — The collateral value of the lines chosen: below the requirement when the inventory ran out, above it when a lot could not be split.
    carryPerDay: 0.0d,  // required — What the chosen lines cost the fund a day to leave locked up, in the base currency.
    allCashCarryPerDay: 0.0d,  // optional — What covering the whole call in base-currency cash would cost a day. Null when the cash rate is unavailable or for a recall.
    candidates: new List<CollateralAllocationCandidate>(),  // required — Every holding considered, ranked ones first by rank, then the excluded with the constraint that excluded them.
    allocation: new List<CollateralAllocationLine>()  // required — The assets chosen, cheapest first, each with what a transaction moving it needs.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CollateralAllocation>(json);
```

- [ResourceId](ResourceId.md)
- [CounterpartyIdentifier](CounterpartyIdentifier.md)
- [CollateralAllocationCandidate](CollateralAllocationCandidate.md) — used in `Candidates`
- [CollateralAllocationLine](CollateralAllocationLine.md) — used in `Allocation`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

