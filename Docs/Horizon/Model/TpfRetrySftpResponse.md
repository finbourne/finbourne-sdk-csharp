# Finbourne.Sdk.Horizon.Model.TpfRetrySftpResponse

Response from retrying SFTP file delivery
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Success** | **bool** | Required | Whether the retry was successful |
| **Message** | **string** | Required | Status message describing the result |
| **NewFileDeliveryId** | **long?** | Optional | ID of the new file delivery record created for this retry (if successful) |
| **RetriedAt** | **DateTimeOffset?** | Optional | Timestamp when the retry was executed |
| **OriginalFile** | [TpfFileDeliveryInfo](TpfFileDeliveryInfo.md) | Optional | *No description available.* |
| **DuplicateFile** | [TpfFileDeliveryInfo](TpfFileDeliveryInfo.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TpfRetrySftpResponse(
    success: true,  // required — Whether the retry was successful
    message: "...",  // required — Status message describing the result
    newFileDeliveryId: 0L,  // optional — ID of the new file delivery record created for this retry (if successful)
    retriedAt: DateTimeOffset.Now,  // optional — Timestamp when the retry was executed
    originalFile: new TpfFileDeliveryInfo(...),  // optional
    duplicateFile: new TpfFileDeliveryInfo(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TpfRetrySftpResponse>(json);
```

- [TpfFileDeliveryInfo](TpfFileDeliveryInfo.md)
- [TpfFileDeliveryInfo](TpfFileDeliveryInfo.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

