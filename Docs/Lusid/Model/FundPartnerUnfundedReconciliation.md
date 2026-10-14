# Finbourne.Sdk.Lusid.Model.FundPartnerUnfundedReconciliation

The unfunded commitment statement of one partner over a period: the register's opening unfunded, the booked  activity that moves it, the closing unfunded that implies, and the register's own closing unfunded it is checked against.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record the statement is for. |
| **FundId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Currency** | **string** | Required | The currency of every amount on the statement, being the commitment currency of the register line. |
| **PeriodFrom** | **DateTimeOffset** | Required | The effective datetime the statement opens at. |
| **PeriodTo** | **DateTimeOffset** | Required | The effective datetime the statement closes at. |
| **OpeningUnfunded** | **decimal** | Required | The unfunded commitment at the opening datetime, from the register. |
| **ContributionsInsideCommitment** | **decimal** | Required | Capital called inside the commitment over the period, which reduces unfunded. Contributions outside the commitment, such as equalisation interest, are listed but do not count here. |
| **RecallableDistributions** | **decimal** | Required | Distributions over the period returned as recallable, which restore unfunded. |
| **ExpiredRecallable** | **decimal** | Required | Recallable distributions whose recall deadline passed in the period without being recalled, which reduce unfunded. |
| **CommitmentChanges** | **decimal** | Required | Changes to the commitment over the period, which move unfunded one for one. |
| **Transfers** | **decimal** | Required | Commitment transferred in or out over the period, which moves unfunded one for one. |
| **ClosingUnfunded** | **decimal** | Required | Opening unfunded less contributions inside the commitment, plus recallable distributions, less expired recallable, plus or minus commitment changes and transfers. |
| **RegisterUnfunded** | **decimal** | Required | The unfunded commitment at the closing datetime, from the register. |
| **Difference** | **decimal** | Required | Closing unfunded less the register&#39;s unfunded at the closing datetime. Zero when the statement ties. |
| **Ties** | **bool** | Required | Whether the closing unfunded equals the register&#39;s unfunded at the closing datetime. |
| **Lines** | [List&lt;FundPartnerUnfundedReconciliationLine&gt;](FundPartnerUnfundedReconciliationLine.md) | Required | Every booked allocation to the partner over the period, in event date order, with the ILPA transaction type each is reported under and its effect on unfunded. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundPartnerUnfundedReconciliation(
    investorRecordId: "...",  // required — The investor record the statement is for.
    fundId: new ResourceId(...),  // required
    currency: "...",  // required — The currency of every amount on the statement, being the commitment currency of the register line.
    periodFrom: DateTimeOffset.Now,  // required — The effective datetime the statement opens at.
    periodTo: DateTimeOffset.Now,  // required — The effective datetime the statement closes at.
    openingUnfunded: 0.0d,  // required — The unfunded commitment at the opening datetime, from the register.
    contributionsInsideCommitment: 0.0d,  // required — Capital called inside the commitment over the period, which reduces unfunded. Contributions outside the commitment, such as equalisation interest, are listed but do not count here.
    recallableDistributions: 0.0d,  // required — Distributions over the period returned as recallable, which restore unfunded.
    expiredRecallable: 0.0d,  // required — Recallable distributions whose recall deadline passed in the period without being recalled, which reduce unfunded.
    commitmentChanges: 0.0d,  // required — Changes to the commitment over the period, which move unfunded one for one.
    transfers: 0.0d,  // required — Commitment transferred in or out over the period, which moves unfunded one for one.
    closingUnfunded: 0.0d,  // required — Opening unfunded less contributions inside the commitment, plus recallable distributions, less expired recallable, plus or minus commitment changes and transfers.
    registerUnfunded: 0.0d,  // required — The unfunded commitment at the closing datetime, from the register.
    difference: 0.0d,  // required — Closing unfunded less the register&#39;s unfunded at the closing datetime. Zero when the statement ties.
    ties: true,  // required — Whether the closing unfunded equals the register&#39;s unfunded at the closing datetime.
    lines: new List<FundPartnerUnfundedReconciliationLine>()  // required — Every booked allocation to the partner over the period, in event date order, with the ILPA transaction type each is reported under and its effect on unfunded.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundPartnerUnfundedReconciliation>(json);
```

- [ResourceId](ResourceId.md)
- [FundPartnerUnfundedReconciliationLine](FundPartnerUnfundedReconciliationLine.md) — used in `Lines`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

