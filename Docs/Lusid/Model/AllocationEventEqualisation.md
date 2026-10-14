# Finbourne.Sdk.Lusid.Model.AllocationEventEqualisation

The terms of a subsequent close an Equalisation Allocation Event applies: the booked prior calls to equalise, the  partners admitted, and how interest, excess and profit and loss are treated.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PriorCallIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | The booked capital calls to equalise, and any earlier equalisation on the same map whose catch-up the admitted partners must also be brought level with. Each must be booked, on the same allocation map and in the same currency. |
| **NewInvestorRecordIds** | **List&lt;string&gt;** | Required | The investor records admitted at this close. Each must be on the register with its commitment at the event date. |
| **InterestRate** | **decimal?** | Optional | The simple annual rate of equalisation interest the admitted partners pay on each catch-up from the prior call&#39;s due date to the event date. Defaults to 0.08. |
| **DayCountConvention** | **string** | Optional | The day count of the equalisation interest: ACT/365 or ACT/360. Defaults to ACT/365. |
| **InterestOnFees** | **bool?** | Optional | Whether equalisation interest is also charged on the management fee catch-ups, from each fee&#39;s due date. Defaults to false. |
| **Treatment** | **string** | Optional | How the existing partners&#39; excess is returned: ReturnOfExcess restores it to their uncalled commitment; RecallableDistribution distributes it as recallable capital. Defaults to ReturnOfExcess. Available values: ReturnOfExcess, RecallableDistribution. |
| **Pnl** | **string** | Optional | Whether profit and loss already allocated is re-trued between partners with no cash so each holds its post-close share (ReTrue), or the equalisation is kept to capital (CapitalOnly). Defaults to ReTrue. Available values: ReTrue, CapitalOnly. |
| **FeeCatchUps** | [List&lt;AllocationEventEqualisationFeeCatchUp&gt;](AllocationEventEqualisationFeeCatchUp.md) | Optional | The management fees each admitted partner owes from the first fee date to the close, including any stub period, as explicit amounts. Paid to the manager and allocated to that partner only. |
| **Marks** | [List&lt;AllocationEventEqualisationMark&gt;](AllocationEventEqualisationMark.md) | Optional | The valuation moves already allocated to the existing partners, by the member of the structure they belong to, to re-true to the admitted partners. Ignored when the profit and loss treatment is CapitalOnly. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventEqualisation(
    priorCallIds: new List<ResourceId>(),  // required — The booked capital calls to equalise, and any earlier equalisation on the same map whose catch-up the admitted partners must also be brought level with. Each must be booked, on the same allocation map and in the same currency.
    newInvestorRecordIds: ,  // required — The investor records admitted at this close. Each must be on the register with its commitment at the event date.
    interestRate: 0.0d,  // optional — The simple annual rate of equalisation interest the admitted partners pay on each catch-up from the prior call&#39;s due date to the event date. Defaults to 0.08.
    dayCountConvention: "...",  // optional — The day count of the equalisation interest: ACT/365 or ACT/360. Defaults to ACT/365.
    interestOnFees: true,  // optional — Whether equalisation interest is also charged on the management fee catch-ups, from each fee&#39;s due date. Defaults to false.
    treatment: "...",  // optional — How the existing partners&#39; excess is returned: ReturnOfExcess restores it to their uncalled commitment; RecallableDistribution distributes it as recallable capital. Defaults to ReturnOfExcess. Available values: ReturnOfExcess, RecallableDistribution.
    pnl: "...",  // optional — Whether profit and loss already allocated is re-trued between partners with no cash so each holds its post-close share (ReTrue), or the equalisation is kept to capital (CapitalOnly). Defaults to ReTrue. Available values: ReTrue, CapitalOnly.
    feeCatchUps: new List<AllocationEventEqualisationFeeCatchUp>(),  // optional — The management fees each admitted partner owes from the first fee date to the close, including any stub period, as explicit amounts. Paid to the manager and allocated to that partner only.
    marks: new List<AllocationEventEqualisationMark>()  // optional — The valuation moves already allocated to the existing partners, by the member of the structure they belong to, to re-true to the admitted partners. Ignored when the profit and loss treatment is CapitalOnly.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventEqualisation>(json);
```


## Related Models

- [ResourceId](ResourceId.md) — used in `PriorCallIds`
- [AllocationEventEqualisationFeeCatchUp](AllocationEventEqualisationFeeCatchUp.md) — used in `FeeCatchUps`
- [AllocationEventEqualisationMark](AllocationEventEqualisationMark.md) — used in `Marks`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

