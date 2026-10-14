# Finbourne.Sdk.Lusid.Model.AllocationEventReversal

How a booked Allocation Event was reversed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Reference** | **string** | Optional | The reference the mirror postings were written under: the original booking reference with a -REV suffix. |
| **Reason** | **string** | Optional | Why the event was reversed. |
| **ReversedAt** | **DateTimeOffset** | Optional | The datetime at which the event was reversed. |
| **EffectiveAt** | **DateTimeOffset** | Optional | The date the mirror postings were posted at. |
| **Backdated** | **bool** | Optional | Whether the mirror postings were posted at the original event date despite the period being closed. |
| **RefundPayable** | [List&lt;AllocationEventRefund&gt;](AllocationEventRefund.md) | Optional | Cash owed back to investors who had already paid in when the event was reversed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventReversal(
    reference: "...",  // optional — The reference the mirror postings were written under: the original booking reference with a -REV suffix.
    reason: "...",  // optional — Why the event was reversed.
    reversedAt: DateTimeOffset.Now,  // optional — The datetime at which the event was reversed.
    effectiveAt: DateTimeOffset.Now,  // optional — The date the mirror postings were posted at.
    backdated: true,  // optional — Whether the mirror postings were posted at the original event date despite the period being closed.
    refundPayable: new List<AllocationEventRefund>()  // optional — Cash owed back to investors who had already paid in when the event was reversed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventReversal>(json);
```

- [AllocationEventRefund](AllocationEventRefund.md) — used in `RefundPayable`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

