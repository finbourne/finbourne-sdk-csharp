# Finbourne.Sdk.Horizon.Model.IntegrationRerunResponse

No content is returned when an instance is rerun.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | [InstanceExecutionReferenceId](InstanceExecutionReferenceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationRerunResponse(
    runId: new InstanceExecutionReferenceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationRerunResponse>(json);
```


## Related Models

- [InstanceExecutionReferenceId](InstanceExecutionReferenceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

