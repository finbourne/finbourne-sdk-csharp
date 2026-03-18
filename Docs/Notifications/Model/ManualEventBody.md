# Finbourne.Sdk.Notifications.Model.ManualEventBody

The body of the manual event
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Subject** | **string** | Required | The subject of the manual event |
| **Message** | **string** | Required | The message of the manual event |
| **JsonMessage** | **Object** | Optional | The JSON message of the manual event |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new ManualEventBody(
    subject: "...",  // required — The subject of the manual event
    message: "...",  // required — The message of the manual event
    jsonMessage:   // optional — The JSON message of the manual event
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ManualEventBody>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

