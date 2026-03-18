# Finbourne.Sdk.Notifications.Model.Notification

A notification object
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NotificationId** | **string** | Required | The identifier of the notification |
| **DisplayName** | **string** | Required | The name of the notification |
| **Description** | **string** | Optional | The summary of the services provided by the notification |
| **NotificationType** | [NotificationTypeResponse](NotificationTypeResponse.md) | Required | *No description available.* |
| **CreatedAt** | **DateTimeOffset** | Required | The time at which the subscription was made |
| **UserIdCreated** | **string** | Required | The user who made the subscription |
| **ModifiedAt** | **DateTimeOffset** | Required | The time at which the subscription was last modified |
| **UserIdModified** | **string** | Required | The user who last modified the subscription |
| **Href** | **string** | Optional | A URI for retrieving this notification |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new Notification(
    notificationId: "...",  // required — The identifier of the notification
    displayName: "...",  // required — The name of the notification
    description: "...",  // optional — The summary of the services provided by the notification
    notificationType: new NotificationTypeResponse(...),  // required
    createdAt: DateTimeOffset.Now,  // required — The time at which the subscription was made
    userIdCreated: "...",  // required — The user who made the subscription
    modifiedAt: DateTimeOffset.Now,  // required — The time at which the subscription was last modified
    userIdModified: "...",  // required — The user who last modified the subscription
    href: "..."  // optional — A URI for retrieving this notification
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

- [NotificationTypeResponse](NotificationTypeResponse.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

