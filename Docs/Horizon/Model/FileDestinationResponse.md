# Finbourne.Sdk.Horizon.Model.FileDestinationResponse

The destination a file delivery row describes. A Failed row carries the per-transaction FailureReason when one was recorded, falling back to the raw Error text.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | *No description available.* |
| **Path** | **string** | Required | *No description available.* |
| **Status** | **string** | Required | *No description available.* |
| **Error** | **string** | Optional | *No description available.* |
| **FailureReason** | **string** | Optional | *No description available.* |
| **Name** | **string** | Optional | The configured destination name, such as the SFTP host, when one was recorded. |
| **DeliveredAt** | **DateTimeOffset?** | Optional | When the file reached the destination; null for a Failed or Pending row. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new FileDestinationResponse(
    type: "...",  // required
    path: "...",  // required
    status: "...",  // required
    error: "...",  // optional
    failureReason: "...",  // optional
    name: "...",  // optional — The configured destination name, such as the SFTP host, when one was recorded.
    deliveredAt: DateTimeOffset.Now  // optional — When the file reached the destination; null for a Failed or Pending row.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FileDestinationResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

