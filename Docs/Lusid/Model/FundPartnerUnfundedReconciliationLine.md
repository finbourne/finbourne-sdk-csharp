# Finbourne.Sdk.Lusid.Model.FundPartnerUnfundedReconciliationLine

One booked allocation to the partner on the unfunded commitment statement.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AllocationEventId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EventDate** | **DateTimeOffset** | Required | The event date of the allocation. |
| **EventType** | **string** | Required | The kind of allocation event: CapitalCall, Distribution, FeeExpense, ValuationMove, Equalisation, RecallExpiry, Transfer, Default or Commitment. |
| **Component** | **string** | Optional | The component of the event the amount belongs to, for example Investment, MgmtFee or ROC. |
| **IlpaTransactionType** | **string** | Required | The ILPA transaction type the line is reported under, from the map&#39;s override or the default for the event type and component. |
| **InsideFund** | **bool** | Required | Whether the flow is inside the fund&#39;s commitment. False for flows outside it, such as equalisation interest or late payment interest, which do not move unfunded. |
| **Amount** | **decimal** | Required | The amount allocated to the partner, in the statement currency. |
| **UnfundedImpact** | **decimal** | Required | The effect of the line on unfunded commitment: negative for a call inside the commitment or an expired recallable, positive for a recallable distribution, and the signed amount for a commitment change or transfer. Zero for a flow that does not move unfunded. |
| **RecallableUntil** | **DateTimeOffset?** | Optional | For a recallable distribution, the last date it may be recalled. Absent when there is no deadline or the line is not recallable. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundPartnerUnfundedReconciliationLine(
    allocationEventId: new ResourceId(...),  // required
    eventDate: DateTimeOffset.Now,  // required — The event date of the allocation.
    eventType: "...",  // required — The kind of allocation event: CapitalCall, Distribution, FeeExpense, ValuationMove, Equalisation, RecallExpiry, Transfer, Default or Commitment.
    component: "...",  // optional — The component of the event the amount belongs to, for example Investment, MgmtFee or ROC.
    ilpaTransactionType: "...",  // required — The ILPA transaction type the line is reported under, from the map&#39;s override or the default for the event type and component.
    insideFund: true,  // required — Whether the flow is inside the fund&#39;s commitment. False for flows outside it, such as equalisation interest or late payment interest, which do not move unfunded.
    amount: 0.0d,  // required — The amount allocated to the partner, in the statement currency.
    unfundedImpact: 0.0d,  // required — The effect of the line on unfunded commitment: negative for a call inside the commitment or an expired recallable, positive for a recallable distribution, and the signed amount for a commitment change or transfer. Zero for a flow that does not move unfunded.
    recallableUntil: DateTimeOffset.Now  // optional — For a recallable distribution, the last date it may be recalled. Absent when there is no deadline or the line is not recallable.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundPartnerUnfundedReconciliationLine>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

