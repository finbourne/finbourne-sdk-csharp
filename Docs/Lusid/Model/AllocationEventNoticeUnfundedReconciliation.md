# Finbourne.Sdk.Lusid.Model.AllocationEventNoticeUnfundedReconciliation

The partner's unfunded commitment rolled through the event on the notice.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Opening** | **decimal** | Required | The unfunded commitment before the event. |
| **Calls** | **decimal** | Required | Capital calls reducing the unfunded commitment. |
| **DistributionsRecallable** | **decimal** | Required | Recallable distributions restoring the unfunded commitment. |
| **Expiries** | **decimal** | Required | Recallable amounts that expired. |
| **CommitmentChanges** | **decimal** | Required | Changes to the commitment itself. |
| **Transfers** | **decimal** | Required | Transfers of unfunded commitment between partners. |
| **Closing** | **decimal** | Required | The unfunded commitment after the event. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventNoticeUnfundedReconciliation(
    opening: 0.0d,  // required — The unfunded commitment before the event.
    calls: 0.0d,  // required — Capital calls reducing the unfunded commitment.
    distributionsRecallable: 0.0d,  // required — Recallable distributions restoring the unfunded commitment.
    expiries: 0.0d,  // required — Recallable amounts that expired.
    commitmentChanges: 0.0d,  // required — Changes to the commitment itself.
    transfers: 0.0d,  // required — Transfers of unfunded commitment between partners.
    closing: 0.0d  // required — The unfunded commitment after the event.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventNoticeUnfundedReconciliation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

