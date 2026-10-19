# Finbourne.Sdk.Lusid.Model.CarryAccrualResult

The outcome of a carry accrual: the movement in each partner's carry against what was last accrued.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PeriodEnd** | **DateTimeOffset** | Required | The date carry is accrued to. |
| **Source** | **string** | Required | The waterfall or model the carry amounts came from. |
| **Lines** | [List&lt;CarryAccrualLine&gt;](CarryAccrualLine.md) | Required | The accrual movement per partner. |
| **BookedTransactionIds** | **List&lt;string&gt;** | Required | The identifiers of the transactions booked, if any. |
| **LaterRunIds** | **List&lt;string&gt;** | Required | The run identifiers of carry accruals already on the ledger with an effective date after this period end. Restating an earlier period moves the to-date balance those runs were accrued against; re-run them to roll the restatement forward. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CarryAccrualResult(
    fundId: new ResourceId(...),  // required
    periodEnd: DateTimeOffset.Now,  // required — The date carry is accrued to.
    source: "...",  // required — The waterfall or model the carry amounts came from.
    lines: new List<CarryAccrualLine>(),  // required — The accrual movement per partner.
    bookedTransactionIds: ,  // required — The identifiers of the transactions booked, if any.
    laterRunIds:   // required — The run identifiers of carry accruals already on the ledger with an effective date after this period end. Restating an earlier period moves the to-date balance those runs were accrued against; re-run them to roll the restatement forward.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CarryAccrualResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [CarryAccrualLine](CarryAccrualLine.md) — used in `Lines`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

