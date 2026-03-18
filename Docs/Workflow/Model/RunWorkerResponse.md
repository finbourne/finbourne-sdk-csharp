# Finbourne.Sdk.Workflow.Model.RunWorkerResponse

The RunWorker response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **Guid** | Required | Identifies a Worker run |
| **StatusDetail** | **string** | Optional | Detail on the final status |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new RunWorkerResponse(
    runId: "...",  // required — Identifies a Worker run
    statusDetail: "..."  // optional — Detail on the final status
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RunWorkerResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

