# Finbourne.Sdk.Workflow.Model.InitialState

Defines the Initial State of the Task
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The Initial State of the Task |
| **RequiredFields** | **List&lt;string&gt;** | Optional | Required input Fields for the Initial State |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new InitialState(
    name: "...",  // required — The Initial State of the Task
    requiredFields:   // optional — Required input Fields for the Initial State
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InitialState>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

