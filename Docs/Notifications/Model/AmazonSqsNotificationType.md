# Finbourne.Sdk.Notifications.Model.AmazonSqsNotificationType

The information required to create or update an AWS SQS notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of delivery mechanism for this notification |
| **ApiKeyRef** | **string** | Required | Reference to API key from Configuration Store |
| **ApiSecretRef** | **string** | Required | Reference to API secret from Configuration Store |
| **Body** | **string** | Required | The body of the Amazon Queue Message |
| **QueueUrlRef** | **string** | Required | Reference to queue url from Configuration Store |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new AmazonSqsNotificationType(
    type: "...",  // required — The type of delivery mechanism for this notification
    apiKeyRef: "...",  // required — Reference to API key from Configuration Store
    apiSecretRef: "...",  // required — Reference to API secret from Configuration Store
    body: "...",  // required — The body of the Amazon Queue Message
    queueUrlRef: "..."  // required — Reference to queue url from Configuration Store
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AmazonSqsNotificationType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

