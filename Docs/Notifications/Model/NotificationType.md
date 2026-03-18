# Finbourne.Sdk.Notifications.Model.NotificationType

Holds information about a Finbourne.Notifications.WebApi.Dtos.Notifications.Notification that is being created

## oneOf Type

`NotificationType` can be one of the following types:

* [AmazonSqsNotificationType](./AmazonSqsNotificationType.md)
* [AmazonSqsPrincipalAuthNotificationType](./AmazonSqsPrincipalAuthNotificationType.md)
* [AzureServiceBusNotificationType](./AzureServiceBusNotificationType.md)
* [EmailNotificationType](./EmailNotificationType.md)
* [SmsNotificationType](./SmsNotificationType.md)
* [WebhookNotificationType](./WebhookNotificationType.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var inner = new AmazonSqsNotificationType(...);
var instance = new NotificationType(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NotificationType>(json);
```

## Related Models

- [AmazonSqsNotificationType](./AmazonSqsNotificationType.md)
- [AmazonSqsPrincipalAuthNotificationType](./AmazonSqsPrincipalAuthNotificationType.md)
- [AzureServiceBusNotificationType](./AzureServiceBusNotificationType.md)
- [EmailNotificationType](./EmailNotificationType.md)
- [SmsNotificationType](./SmsNotificationType.md)
- [WebhookNotificationType](./WebhookNotificationType.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

