# Finbourne.Sdk.Lusid.Model.AllocationPaymentHold

A hold placed on a partner's payment against an allocation event, blocking receipt until it is released  by a second user.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AllocationEventId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InvestorRecordId** | **string** | Required | The investor record identifier of the partner whose payment is held. |
| **Status** | **string** | Required | The hold status: Blocked, Escrow or Released. |
| **Reason** | **string** | Optional | The reason for the hold. |
| **Reference** | **string** | Optional | An external reference for the hold, such as a compliance case number. |
| **PlacedBy** | **string** | Required | The user who placed the hold. |
| **PlacedAt** | **DateTimeOffset** | Required | When the hold was placed. |
| **ReleasedBy** | **string** | Optional | The user who released the hold, or null while it is active. |
| **ReleasedAt** | **DateTimeOffset?** | Optional | When the hold was released, or null while it is active. |
| **Active** | **bool** | Required | Whether the hold is currently blocking receipt of the partner&#39;s payment. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationPaymentHold(
    allocationEventId: new ResourceId(...),  // required
    investorRecordId: "...",  // required — The investor record identifier of the partner whose payment is held.
    status: "...",  // required — The hold status: Blocked, Escrow or Released.
    reason: "...",  // optional — The reason for the hold.
    reference: "...",  // optional — An external reference for the hold, such as a compliance case number.
    placedBy: "...",  // required — The user who placed the hold.
    placedAt: DateTimeOffset.Now,  // required — When the hold was placed.
    releasedBy: "...",  // optional — The user who released the hold, or null while it is active.
    releasedAt: DateTimeOffset.Now,  // optional — When the hold was released, or null while it is active.
    active: true  // required — Whether the hold is currently blocking receipt of the partner&#39;s payment.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationPaymentHold>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

