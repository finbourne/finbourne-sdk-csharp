# Finbourne.Sdk.Lusid.Model.PartnerCapitalAccountMemo

The memo block of a capital account statement: commitment balances from the register at the period end.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Commitment** | **decimal** | Required | The partner&#39;s total commitment. |
| **UncalledCommitment** | **decimal** | Required | The commitment not yet called. |
| **Recallable** | **decimal** | Required | Distributions that the fund may recall. |
| **AvailableCommitment** | **decimal** | Required | The commitment available to call, being uncalled plus recallable. |
| **ContributionsReceivable** | **decimal?** | Optional | Called contributions not yet received from the partner, counting capital that was returned as recallable and has since been recalled. Omitted while a register line of the partner that has had returned capital marked recallable has not been rebuilt with recalled capital as a balance, since the figure could then miss an unpaid recall; the declared distributions are then served gross. |
| **DistributionsDeclaredNotPaid** | **decimal** | Required | Distributions declared to the partner but not yet paid. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerCapitalAccountMemo(
    commitment: 0.0d,  // required — The partner&#39;s total commitment.
    uncalledCommitment: 0.0d,  // required — The commitment not yet called.
    recallable: 0.0d,  // required — Distributions that the fund may recall.
    availableCommitment: 0.0d,  // required — The commitment available to call, being uncalled plus recallable.
    contributionsReceivable: 0.0d,  // optional — Called contributions not yet received from the partner, counting capital that was returned as recallable and has since been recalled. Omitted while a register line of the partner that has had returned capital marked recallable has not been rebuilt with recalled capital as a balance, since the figure could then miss an unpaid recall; the declared distributions are then served gross.
    distributionsDeclaredNotPaid: 0.0d  // required — Distributions declared to the partner but not yet paid.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerCapitalAccountMemo>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

