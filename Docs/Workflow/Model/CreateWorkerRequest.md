# Finbourne.Sdk.Workflow.Model.CreateWorkerRequest

Request to Create a new worker
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | Human readable name |
| **Description** | **string** | Optional | Human readable description |
| **WorkerConfiguration** | [WorkerConfiguration](WorkerConfiguration.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CreateWorkerRequest(
    id: new ResourceId(...),  // required
    displayName: "...",  // required — Human readable name
    description: "...",  // optional — Human readable description
    workerConfiguration: new WorkerConfiguration(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateWorkerRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [WorkerConfiguration](WorkerConfiguration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

