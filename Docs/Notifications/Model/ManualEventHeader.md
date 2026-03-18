# Finbourne.Sdk.Notifications.Model.ManualEventHeader

The header of the manual event
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EventType** | **string** | Optional | The event type of the manual event *(read-only)* |
| **Timestamp** | **DateTimeOffset** | Optional | The timestamp of the manual event |
| **UserId** | **string** | Optional | The user ID of the manual event |
| **RequestId** | **string** | Optional | The request ID of the manual event |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new ManualEventHeader(
    eventType: "...",  // optional — The event type of the manual event
    timestamp: DateTimeOffset.Now,  // optional — The timestamp of the manual event
    userId: "...",  // optional — The user ID of the manual event
    requestId: "..."  // optional — The request ID of the manual event
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ManualEventHeader>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

