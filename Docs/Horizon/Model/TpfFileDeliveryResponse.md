# Finbourne.Sdk.Horizon.Model.TpfFileDeliveryResponse

Response model for TPF file delivery search results
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **string** | Optional | *No description available.* |
| **RunStartTime** | **DateTimeOffset?** | Optional | *No description available.* |
| **FileName** | **string** | Required | *No description available.* |
| **GeneratedAt** | **DateTimeOffset** | Required | When the file was built, or when the attempt failed before a file was built. |
| **RowCount** | **int** | Required | *No description available.* |
| **FileHash** | **string** | Optional | *No description available.* |
| **DestinationType** | **string** | Required | *No description available.* |
| **DestinationPath** | **string** | Optional | *No description available.* |
| **DestinationStatus** | **string** | Required | *No description available.* |
| **DestinationError** | **string** | Optional | *No description available.* |
| **DestinationName** | **string** | Optional | *No description available.* |
| **FileUuid** | **Guid** | Required | *No description available.* |
| **CanResend** | **bool** | Required | Whether the data the file is rebuilt from is still retained, so a resend can be requested. |
| **DeliveredAt** | **DateTimeOffset?** | Optional | When the file reached the destination; null for a Failed or Pending row. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TpfFileDeliveryResponse(
    runId: "...",  // optional
    runStartTime: DateTimeOffset.Now,  // optional
    fileName: "...",  // required
    generatedAt: DateTimeOffset.Now,  // required — When the file was built, or when the attempt failed before a file was built.
    rowCount: 0,  // required
    fileHash: "...",  // optional
    destinationType: "...",  // required
    destinationPath: "...",  // optional
    destinationStatus: "...",  // required
    destinationError: "...",  // optional
    destinationName: "...",  // optional
    fileUuid: "...",  // required
    canResend: true,  // required — Whether the data the file is rebuilt from is still retained, so a resend can be requested.
    deliveredAt: DateTimeOffset.Now  // optional — When the file reached the destination; null for a Failed or Pending row.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TpfFileDeliveryResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

