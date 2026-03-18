# Finbourne.Sdk.Workflow.Model.GetWorkerResultResponse

The RunWorker response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WorkerStatus** | **string** | Required | The final status of the Worker |
| **Results** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** | Required | Results |
| **StatusDetail** | **string** | Optional | Detail on the final status |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new GetWorkerResultResponse(
    workerStatus: "...",  // required — The final status of the Worker
    results: ,  // required — Results
    statusDetail: "..."  // optional — Detail on the final status
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GetWorkerResultResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

