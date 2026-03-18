# Finbourne.Sdk.Notifications.Model.NotificationTypeResponse

Holds readonly information about a Finbourne.Notifications.WebApi.Dtos.Notifications.Notification

## oneOf Type

`NotificationTypeResponse` can be one of the following types:

* [AmazonSqsNotificationTypeResponse](./AmazonSqsNotificationTypeResponse.md)
* [AmazonSqsPrincipalAuthNotificationTypeResponse](./AmazonSqsPrincipalAuthNotificationTypeResponse.md)
* [AzureServiceBusTypeResponse](./AzureServiceBusTypeResponse.md)
* [EmailNotificationTypeResponse](./EmailNotificationTypeResponse.md)
* [SmsNotificationTypeResponse](./SmsNotificationTypeResponse.md)
* [WebhookNotificationTypeResponse](./WebhookNotificationTypeResponse.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var inner = new AmazonSqsNotificationTypeResponse(...);
var instance = new NotificationTypeResponse(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NotificationTypeResponse>(json);
```

## Related Models

- [AmazonSqsNotificationTypeResponse](./AmazonSqsNotificationTypeResponse.md)
- [AmazonSqsPrincipalAuthNotificationTypeResponse](./AmazonSqsPrincipalAuthNotificationTypeResponse.md)
- [AzureServiceBusTypeResponse](./AzureServiceBusTypeResponse.md)
- [EmailNotificationTypeResponse](./EmailNotificationTypeResponse.md)
- [SmsNotificationTypeResponse](./SmsNotificationTypeResponse.md)
- [WebhookNotificationTypeResponse](./WebhookNotificationTypeResponse.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

