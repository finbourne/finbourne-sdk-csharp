# Finbourne.Sdk.Workflow.Model.CreateChildTasksAction

Defines a Create Child Tasks Action
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | Type name for this Action |
| **ChildTaskConfigurations** | [List&lt;CreateChildTaskConfiguration&gt;](CreateChildTaskConfiguration.md) | Required | The Child Task Configurations |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CreateChildTasksAction(
    type: "...",  // required — Type name for this Action
    childTaskConfigurations: new List<CreateChildTaskConfiguration>()  // required — The Child Task Configurations
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateChildTasksAction>(json);
```

- [CreateChildTaskConfiguration](CreateChildTaskConfiguration.md) — used in `ChildTaskConfigurations`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

