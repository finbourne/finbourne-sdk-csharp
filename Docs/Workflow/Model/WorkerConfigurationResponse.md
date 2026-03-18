# Finbourne.Sdk.Workflow.Model.WorkerConfigurationResponse

Readonly information about how the worker should be executed

## oneOf Type

`WorkerConfigurationResponse` can be one of the following types:

* [FailResponse](./FailResponse.md)
* [GroupReconciliationResponse](./GroupReconciliationResponse.md)
* [HealthCheckResponse](./HealthCheckResponse.md)
* [LibraryResponse](./LibraryResponse.md)
* [LuminesceViewResponse](./LuminesceViewResponse.md)
* [LusidEntityDataQualityCheckResponse](./LusidEntityDataQualityCheckResponse.md)
* [SchedulerJobResponse](./SchedulerJobResponse.md)
* [SleepResponse](./SleepResponse.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var inner = new FailResponse(...);
var instance = new WorkerConfigurationResponse(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkerConfigurationResponse>(json);
```

## Related Models

- [FailResponse](./FailResponse.md)
- [GroupReconciliationResponse](./GroupReconciliationResponse.md)
- [HealthCheckResponse](./HealthCheckResponse.md)
- [LibraryResponse](./LibraryResponse.md)
- [LuminesceViewResponse](./LuminesceViewResponse.md)
- [LusidEntityDataQualityCheckResponse](./LusidEntityDataQualityCheckResponse.md)
- [SchedulerJobResponse](./SchedulerJobResponse.md)
- [SleepResponse](./SleepResponse.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

