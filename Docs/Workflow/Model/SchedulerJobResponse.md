# Finbourne.Sdk.Workflow.Model.SchedulerJobResponse

Readonly configuration for a Worker that calls a Scheduler job
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of worker |
| **JobId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new SchedulerJobResponse(
    type: "...",  // optional — The type of worker
    jobId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SchedulerJobResponse>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

