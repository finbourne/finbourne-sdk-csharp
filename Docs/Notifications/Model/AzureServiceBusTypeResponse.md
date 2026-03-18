# Finbourne.Sdk.Notifications.Model.AzureServiceBusTypeResponse

Holds readonly information about an Azure Service Bus notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of delivery mechanism for this notification |
| **NamespaceRef** | **string** | Optional | Reference to namespace from Configuration Store |
| **QueueNameRef** | **string** | Optional | Reference to queue name from Configuration Store |
| **Body** | **string** | Optional | The body of the Azure service bus Message |
| **TenantIdRef** | **string** | Optional | Reference to tenant id  from Configuration Store |
| **ClientIdRef** | **string** | Optional | Reference to client id from Configuration Store |
| **ClientSecretRef** | **string** | Optional | Reference to client secret from Configuration Store |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new AzureServiceBusTypeResponse(
    type: "...",  // optional — The type of delivery mechanism for this notification
    namespaceRef: "...",  // optional — Reference to namespace from Configuration Store
    queueNameRef: "...",  // optional — Reference to queue name from Configuration Store
    body: "...",  // optional — The body of the Azure service bus Message
    tenantIdRef: "...",  // optional — Reference to tenant id  from Configuration Store
    clientIdRef: "...",  // optional — Reference to client id from Configuration Store
    clientSecretRef: "..."  // optional — Reference to client secret from Configuration Store
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AzureServiceBusTypeResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

