# Finbourne.Sdk.Notifications.Model.AzureServiceBusNotificationType

The information required to create or update an Azure Service Bus notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of delivery mechanism for this notification |
| **Namespace** | **string** | Required | Reference to namespace from Configuration Store |
| **QueueName** | **string** | Required | Reference to queue name from Configuration Store |
| **Body** | **string** | Required | The body of the Azure Service Bus Message |
| **TenantId** | **string** | Required | Reference to tenant id from Configuration Store |
| **ClientId** | **string** | Required | Reference to client id from Configuration Store |
| **ClientSecret** | **string** | Required | Reference to client secret from Configuration Store |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new AzureServiceBusNotificationType(
    type: "...",  // required — The type of delivery mechanism for this notification
    varNamespace: "...",  // required — Reference to namespace from Configuration Store
    queueName: "...",  // required — Reference to queue name from Configuration Store
    body: "...",  // required — The body of the Azure Service Bus Message
    tenantId: "...",  // required — Reference to tenant id from Configuration Store
    clientId: "...",  // required — Reference to client id from Configuration Store
    clientSecret: "..."  // required — Reference to client secret from Configuration Store
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AzureServiceBusNotificationType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

