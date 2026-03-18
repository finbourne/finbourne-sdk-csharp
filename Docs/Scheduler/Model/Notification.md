# Finbourne.Sdk.Scheduler.Model.Notification

Notification type
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FireOn** | **string** | Optional | Condition for the notification *(read-only)* |
| **Transport** | **string** | Optional | The type of the notification |
| **Destination** | **List&lt;string&gt;** | Optional | Where the notification should be sent |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new Notification(
    fireOn: "...",  // optional — Condition for the notification
    transport: "...",  // optional — The type of the notification
    destination:   // optional — Where the notification should be sent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Notification>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

