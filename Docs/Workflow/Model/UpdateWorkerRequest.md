# Finbourne.Sdk.Workflow.Model.UpdateWorkerRequest

Request to Update a new worker
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | Human readable name |
| **Description** | **string** | Optional | Human readable description |
| **WorkerConfiguration** | **Object** | Required | Information about how the worker should be executed |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new UpdateWorkerRequest(
    displayName: "...",  // required — Human readable name
    description: "...",  // optional — Human readable description
    workerConfiguration:   // required — Information about how the worker should be executed
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateWorkerRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

