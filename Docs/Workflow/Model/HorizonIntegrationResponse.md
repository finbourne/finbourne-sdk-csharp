# Finbourne.Sdk.Workflow.Model.HorizonIntegrationResponse

Readonly configuration for the Horizon Integration Worker
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of worker |
| **IntegrationInstanceId** | **string** | Optional | The id of the Horizon integration instance the worker executes. Null on the library worker. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new HorizonIntegrationResponse(
    type: "...",  // optional — The type of worker
    integrationInstanceId: "..."  // optional — The id of the Horizon integration instance the worker executes. Null on the library worker.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HorizonIntegrationResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

