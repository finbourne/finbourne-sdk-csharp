# Finbourne.Sdk.Lusid.Model.ExecutionSetRequest

A request to create or update multiple Executions.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Requests** | [List&lt;ExecutionRequest&gt;](ExecutionRequest.md) | Optional | A collection of ExecutionRequests. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExecutionSetRequest(
    requests: new List<ExecutionRequest>()  // optional — A collection of ExecutionRequests.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExecutionSetRequest>(json);
```


## Related Models

- [ExecutionRequest](ExecutionRequest.md) — used in `Requests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

