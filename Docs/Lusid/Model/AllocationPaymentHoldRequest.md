# Finbourne.Sdk.Lusid.Model.AllocationPaymentHoldRequest

The request used to place, move or release a hold on a partner's payment against an allocation event.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Required | The hold status to set: Blocked, Escrow or Released. A hold may only be released by a different user from the one who placed it. |
| **Reason** | **string** | Optional | The reason for the hold. |
| **Reference** | **string** | Optional | An external reference for the hold, such as a compliance case number. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationPaymentHoldRequest(
    status: "...",  // required — The hold status to set: Blocked, Escrow or Released. A hold may only be released by a different user from the one who placed it.
    reason: "...",  // optional — The reason for the hold.
    reference: "..."  // optional — An external reference for the hold, such as a compliance case number.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationPaymentHoldRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

