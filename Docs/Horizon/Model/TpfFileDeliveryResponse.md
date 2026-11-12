# Finbourne.Sdk.Horizon.Model.TpfFileDeliveryResponse

Response model for TPF file delivery search results
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **string** | Optional | The run id of the latest execution attempt in this row&#39;s run chain (the root run, its automatic retries and resends); equals referenceId when the chain has a single attempt or no recorded execution. |
| **RunStartTime** | **DateTimeOffset?** | Optional | When the row&#39;s root run started (the batch start), not the latest attempt&#39;s start. |
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
| **Attempt** | **int?** | Optional | The highest attempt number (1-based) made for this delivery&#39;s run, including automatic retries and resends. |
| **ReferenceId** | **string** | Optional | The root run id of this row&#39;s run chain, the same value run history reports as referenceId. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TpfFileDeliveryResponse(
    runId: "...",  // optional — The run id of the latest execution attempt in this row&#39;s run chain (the root run, its automatic retries and resends); equals referenceId when the chain has a single attempt or no recorded execution.
    runStartTime: DateTimeOffset.Now,  // optional — When the row&#39;s root run started (the batch start), not the latest attempt&#39;s start.
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
    deliveredAt: DateTimeOffset.Now,  // optional — When the file reached the destination; null for a Failed or Pending row.
    attempt: 0,  // optional — The highest attempt number (1-based) made for this delivery&#39;s run, including automatic retries and resends.
    referenceId: "..."  // optional — The root run id of this row&#39;s run chain, the same value run history reports as referenceId.
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

