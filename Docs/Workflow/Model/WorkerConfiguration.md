# Finbourne.Sdk.Workflow.Model.WorkerConfiguration

Information about how the worker should be executed

## oneOf Type

`WorkerConfiguration` can be one of the following types:

* [Fail](./Fail.md)
* [GroupReconciliation](./GroupReconciliation.md)
* [HealthCheck](./HealthCheck.md)
* [LuminesceView](./LuminesceView.md)
* [LusidEntityDataQualityCheck](./LusidEntityDataQualityCheck.md)
* [SchedulerJob](./SchedulerJob.md)
* [Sleep](./Sleep.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var inner = new Fail(...);
var instance = new WorkerConfiguration(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkerConfiguration>(json);
```

## Related Models

- [Fail](./Fail.md)
- [GroupReconciliation](./GroupReconciliation.md)
- [HealthCheck](./HealthCheck.md)
- [LuminesceView](./LuminesceView.md)
- [LusidEntityDataQualityCheck](./LusidEntityDataQualityCheck.md)
- [SchedulerJob](./SchedulerJob.md)
- [Sleep](./Sleep.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

