# Finbourne.Sdk.Notifications.Model.UpdateNotificationRequest

The information required to update a notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the notification |
| **Description** | **string** | Optional | The summary of the services provided by the notification |
| **NotificationType** | [NotificationType](NotificationType.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new UpdateNotificationRequest(
    displayName: "...",  // required — The name of the notification
    description: "...",  // optional — The summary of the services provided by the notification
    notificationType: new NotificationType(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateNotificationRequest>(json);
```

- [NotificationType](NotificationType.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

