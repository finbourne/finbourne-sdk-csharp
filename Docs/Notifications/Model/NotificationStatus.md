# Finbourne.Sdk.Notifications.Model.NotificationStatus

The status object of a notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Result** | **string** | Optional | The status of the notification |
| **LastUpdated** | **DateTimeOffset** | Optional | The time at which the notification status was last updated |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new NotificationStatus(
    result: "...",  // optional — The status of the notification
    lastUpdated: DateTimeOffset.Now  // optional — The time at which the notification status was last updated
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NotificationStatus>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

