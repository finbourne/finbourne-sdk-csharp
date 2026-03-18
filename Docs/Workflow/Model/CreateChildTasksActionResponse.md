# Finbourne.Sdk.Workflow.Model.CreateChildTasksActionResponse

Defines a read-only Create Child Tasks Action
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | Type name for this Action |
| **ChildTaskConfigurations** | [List&lt;CreateChildTaskConfiguration&gt;](CreateChildTaskConfiguration.md) | Optional | The Child Task Configurations |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CreateChildTasksActionResponse(
    type: "...",  // optional — Type name for this Action
    childTaskConfigurations: new List<CreateChildTaskConfiguration>()  // optional — The Child Task Configurations
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateChildTasksActionResponse>(json);
```

- [CreateChildTaskConfiguration](CreateChildTaskConfiguration.md) — used in `ChildTaskConfigurations`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

