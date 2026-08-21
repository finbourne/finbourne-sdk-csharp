# Finbourne.Sdk.Horizon.Model.TpfFileDeliveryInfo

Information about a file delivery
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FileUuid** | **Guid** | Required | File delivery UUID — the identifier the retry endpoint accepts |
| **FileName** | **string** | Required | File name |
| **FileHash** | **string** | Required | SHA-256 hash of the file content |
| **DestinationPath** | **string** | Required | SFTP destination path |
| **Status** | **string** | Required | Delivery status |
| **GeneratedAt** | **DateTimeOffset** | Required | Timestamp when the file was originally generated |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TpfFileDeliveryInfo(
    fileUuid: "...",  // required — File delivery UUID — the identifier the retry endpoint accepts
    fileName: "...",  // required — File name
    fileHash: "...",  // required — SHA-256 hash of the file content
    destinationPath: "...",  // required — SFTP destination path
    status: "...",  // required — Delivery status
    generatedAt: DateTimeOffset.Now  // required — Timestamp when the file was originally generated
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TpfFileDeliveryInfo>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

