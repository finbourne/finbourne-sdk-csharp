# Finbourne.Sdk.Workflow.Model.ActionDetailsResponse

Abstracts the kinds of Actions available in a read-only form

## oneOf Type

`ActionDetailsResponse` can be one of the following types:

* [CreateChildTasksActionResponse](./CreateChildTasksActionResponse.md)
* [RunWorkerActionResponse](./RunWorkerActionResponse.md)
* [TriggerParentTaskActionResponse](./TriggerParentTaskActionResponse.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var inner = new CreateChildTasksActionResponse(...);
var instance = new ActionDetailsResponse(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ActionDetailsResponse>(json);
```

## Related Models

- [CreateChildTasksActionResponse](./CreateChildTasksActionResponse.md)
- [RunWorkerActionResponse](./RunWorkerActionResponse.md)
- [TriggerParentTaskActionResponse](./TriggerParentTaskActionResponse.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

