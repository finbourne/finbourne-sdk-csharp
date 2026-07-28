# Finbourne.Sdk.Lusid.Model.PaymentInstructionStatus

The current status of a Payment Instruction. Managed exclusively via the dedicated  status transition API — not accepted on upsert.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CurrentValue** | **string** | Required | The current status value. One of: Created, Staged, Released, Instructed, Sent, Cancelled. |
| **AsAtLastTransition** | **DateTimeOffset** | Required | The as-at timestamp of the most recent status transition. |
| **UserIdLastTransition** | **string** | Required | The ID of the user who made the most recent status transition. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PaymentInstructionStatus(
    currentValue: "...",  // required — The current status value. One of: Created, Staged, Released, Instructed, Sent, Cancelled.
    asAtLastTransition: DateTimeOffset.Now,  // required — The as-at timestamp of the most recent status transition.
    userIdLastTransition: "..."  // required — The ID of the user who made the most recent status transition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PaymentInstructionStatus>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

