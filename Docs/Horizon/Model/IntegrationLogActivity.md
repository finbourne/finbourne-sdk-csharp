# Finbourne.Sdk.Horizon.Model.IntegrationLogActivity

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Timestamp** | **DateTimeOffset** | Required | *No description available.* |
| **ResultingStatus** | **string** | Required | *No description available.* |
| **MessageType** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationLogActivity(
    timestamp: DateTimeOffset.Now,  // required
    resultingStatus: "...",  // required
    messageType: "...",  // optional
    description: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationLogActivity>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

