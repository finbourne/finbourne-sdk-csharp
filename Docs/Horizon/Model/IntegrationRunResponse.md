# Finbourne.Sdk.Horizon.Model.IntegrationRunResponse

Integration run response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **Guid** | Required | *No description available.* |
| **RefRunId** | **Guid?** | Optional | *No description available.* |
| **Attempt** | **int** | Required | *No description available.* |
| **InstanceId** | **Guid?** | Optional | *No description available.* |
| **InstanceName** | **string** | Optional | *No description available.* |
| **Status** | **string** | Optional | *No description available.* |
| **Message** | **string** | Optional | *No description available.* |
| **Integration** | [IntegrationRunIntegration](IntegrationRunIntegration.md) | Required | *No description available.* |
| **VarVersion** | [IntegrationRunVersion](IntegrationRunVersion.md) | Required | *No description available.* |
| **IntegrationLogs** | **Dictionary&lt;string, Dictionary&lt;string, IntegrationRunLog&gt;&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationRunResponse(
    runId: "...",  // required
    refRunId: "...",  // optional
    attempt: 0,  // required
    instanceId: "...",  // optional
    instanceName: "...",  // optional
    status: "...",  // optional
    message: "...",  // optional
    integration: new IntegrationRunIntegration(...),  // required
    varVersion: new IntegrationRunVersion(...),  // required
    integrationLogs:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationRunResponse>(json);
```

- [IntegrationRunIntegration](IntegrationRunIntegration.md)
- [IntegrationRunVersion](IntegrationRunVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

