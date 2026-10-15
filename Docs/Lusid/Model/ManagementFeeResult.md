# Finbourne.Sdk.Lusid.Model.ManagementFeeResult

The outcome of a management fee calculation.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PeriodStart** | **DateTimeOffset** | Required | The start of the fee period, exclusive. |
| **PeriodEnd** | **DateTimeOffset** | Required | The end of the fee period, inclusive. |
| **Basis** | **string** | Required | The capital base the fee is charged on. Available values: Auto, CommittedCapital, InvestedCapital. Auto charges on committed capital until the investment period ends and on invested capital after. |
| **Lines** | [List&lt;ManagementFeeLine&gt;](ManagementFeeLine.md) | Required | The fee per partner. |
| **Totals** | [ManagementFeeTotals](ManagementFeeTotals.md) | Required | *No description available.* |
| **BookedTransactionIds** | **List&lt;string&gt;** | Required | The identifiers of the transactions booked, if any. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ManagementFeeResult(
    fundId: new ResourceId(...),  // required
    periodStart: DateTimeOffset.Now,  // required — The start of the fee period, exclusive.
    periodEnd: DateTimeOffset.Now,  // required — The end of the fee period, inclusive.
    basis: "...",  // required — The capital base the fee is charged on. Available values: Auto, CommittedCapital, InvestedCapital. Auto charges on committed capital until the investment period ends and on invested capital after.
    lines: new List<ManagementFeeLine>(),  // required — The fee per partner.
    totals: new ManagementFeeTotals(...),  // required
    bookedTransactionIds:   // required — The identifiers of the transactions booked, if any.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ManagementFeeResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ManagementFeeLine](ManagementFeeLine.md) — used in `Lines`
- [ManagementFeeTotals](ManagementFeeTotals.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

