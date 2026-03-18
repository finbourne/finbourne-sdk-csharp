# Finbourne.Sdk.Notifications.Model.Delivery

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **Guid** | Required | The identifier of the delivery. |
| **EventId** | **string** | Required | The identifier of the associated event. |
| **SubscriptionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **NotificationId** | **string** | Required | The identifier of the associated notification. |
| **DeliveryChannel** | **string** | Required | The delivery channel of the message. |
| **MessageDetails** | **string** | Required | The Details of the delivery message as JSON string. |
| **Attempts** | [List&lt;Attempt&gt;](Attempt.md) | Required | A list of all the delivery attempts made for this message. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new Delivery(
    id: "...",  // required — The identifier of the delivery.
    eventId: "...",  // required — The identifier of the associated event.
    subscriptionId: new ResourceId(...),  // required
    notificationId: "...",  // required — The identifier of the associated notification.
    deliveryChannel: "...",  // required — The delivery channel of the message.
    messageDetails: "...",  // required — The Details of the delivery message as JSON string.
    attempts: new List<Attempt>()  // required — A list of all the delivery attempts made for this message.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Delivery>(json);
```

- [ResourceId](ResourceId.md)
- [Attempt](Attempt.md) — used in `Attempts`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

