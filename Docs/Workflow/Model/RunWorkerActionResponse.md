# Finbourne.Sdk.Workflow.Model.RunWorkerActionResponse

Defines a read-only Run Worker Action
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | Type name for this Action |
| **WorkerId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **WorkerAsAt** | **DateTimeOffset?** | Optional | Worker AsAt |
| **WorkerParameters** | [Dictionary&lt;string, FieldMapping&gt;](FieldMapping.md) | Optional | Parameters for this Worker |
| **WorkerStatusTriggers** | [WorkerStatusTriggers](WorkerStatusTriggers.md) | Optional | *No description available.* |
| **ChildTaskConfigurations** | [List&lt;ResultantChildTaskConfiguration&gt;](ResultantChildTaskConfiguration.md) | Optional | Tasks can be generated from run worker results; this is the configuration |
| **WorkerTimeout** | **int?** | Optional | Worker timeout in seconds |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new RunWorkerActionResponse(
    type: "...",  // optional — Type name for this Action
    workerId: new ResourceId(...),  // optional
    workerAsAt: DateTimeOffset.Now,  // optional — Worker AsAt
    workerParameters: new FieldMapping(...),  // optional — Parameters for this Worker
    workerStatusTriggers: new WorkerStatusTriggers(...),  // optional
    childTaskConfigurations: new List<ResultantChildTaskConfiguration>(),  // optional — Tasks can be generated from run worker results; this is the configuration
    workerTimeout: 0  // optional — Worker timeout in seconds
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RunWorkerActionResponse>(json);
```

- [ResourceId](ResourceId.md)
- [FieldMapping](FieldMapping.md) — used in `WorkerParameters`
- [WorkerStatusTriggers](WorkerStatusTriggers.md)
- [ResultantChildTaskConfiguration](ResultantChildTaskConfiguration.md) — used in `ChildTaskConfigurations`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

