# Finbourne.Sdk.Notifications.Model.CreateNotificationRequest

The information required to create a notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NotificationId** | **string** | Required | The identifier of the notification. |
| **DisplayName** | **string** | Required | The name of the notification |
| **Description** | **string** | Optional | The summary of the services provided by the notification |
| **NotificationType** | [NotificationType](NotificationType.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new CreateNotificationRequest(
    notificationId: "...",  // required — The identifier of the notification.
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
var instance = JsonConvert.DeserializeObject<CreateNotificationRequest>(json);
```

- [NotificationType](NotificationType.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

