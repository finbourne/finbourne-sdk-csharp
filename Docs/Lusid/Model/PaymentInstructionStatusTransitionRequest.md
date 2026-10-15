# Finbourne.Sdk.Lusid.Model.PaymentInstructionStatusTransitionRequest

A request to move one Payment Instruction to a new status.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Status** | **string** | Required | The status to move the Payment Instruction to. One of: Created, Staged, Released, Instructed, Sent, Cancelled, Failed. The transition must be permitted from the instruction&#39;s current status. Available values: Created, Staged, Released, Instructed, Sent, Cancelled, Failed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PaymentInstructionStatusTransitionRequest(
    id: new ResourceId(...),  // required
    status: "..."  // required — The status to move the Payment Instruction to. One of: Created, Staged, Released, Instructed, Sent, Cancelled, Failed. The transition must be permitted from the instruction&#39;s current status. Available values: Created, Staged, Released, Instructed, Sent, Cancelled, Failed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PaymentInstructionStatusTransitionRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

