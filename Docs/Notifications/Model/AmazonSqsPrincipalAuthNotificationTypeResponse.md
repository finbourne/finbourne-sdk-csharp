# Finbourne.Sdk.Notifications.Model.AmazonSqsPrincipalAuthNotificationTypeResponse

Holds readonly information about an AWS SQS with Principal Authentication notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of delivery mechanism for this notification |
| **Body** | **string** | Optional | The body of the Amazon Queue Message |
| **QueueUrlRef** | **string** | Optional | Reference to queue url from Configuration Store |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new AmazonSqsPrincipalAuthNotificationTypeResponse(
    type: "...",  // optional — The type of delivery mechanism for this notification
    body: "...",  // optional — The body of the Amazon Queue Message
    queueUrlRef: "..."  // optional — Reference to queue url from Configuration Store
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AmazonSqsPrincipalAuthNotificationTypeResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

