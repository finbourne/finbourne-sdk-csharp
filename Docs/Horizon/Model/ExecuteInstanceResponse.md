# Finbourne.Sdk.Horizon.Model.ExecuteInstanceResponse

Response for executing an instance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExecutionId** | **string** | Required | Identifier for the execution of the integration instance |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ExecuteInstanceResponse(
    executionId: "..."  // required — Identifier for the execution of the integration instance
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExecuteInstanceResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

