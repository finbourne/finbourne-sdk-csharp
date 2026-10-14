# Finbourne.Sdk.Lusid.Model.FundPartnerBalances

The capital balances of one register line, in the commitment currency.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Committed** | **decimal** | Required | The committed capital. |
| **UncalledCommitment** | **decimal** | Required | The commitment not yet called. |
| **PaidIn** | **decimal** | Required | The capital paid in. |
| **Returned** | **decimal** | Required | The capital returned. |
| **Recallable** | **decimal** | Required | The returned capital that may be recalled. |
| **Unfunded** | **decimal** | Required | The unfunded capital. |
| **Funded** | **decimal** | Required | The funded capital. |
| **OutstandingCalls** | **decimal?** | Optional | Capital called but not yet paid in. Omitted on a register line that has had returned capital marked recallable, since recalled capital is not yet tracked as a balance and the figure would exclude it. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundPartnerBalances(
    committed: 0.0d,  // required — The committed capital.
    uncalledCommitment: 0.0d,  // required — The commitment not yet called.
    paidIn: 0.0d,  // required — The capital paid in.
    returned: 0.0d,  // required — The capital returned.
    recallable: 0.0d,  // required — The returned capital that may be recalled.
    unfunded: 0.0d,  // required — The unfunded capital.
    funded: 0.0d,  // required — The funded capital.
    outstandingCalls: 0.0d  // optional — Capital called but not yet paid in. Omitted on a register line that has had returned capital marked recallable, since recalled capital is not yet tracked as a balance and the figure would exclude it.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundPartnerBalances>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

