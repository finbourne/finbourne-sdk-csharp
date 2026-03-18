# Finbourne.Sdk.Workflow.Model.ReadOnlyStates

Information about which states the field can be edited in
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StateType** | **string** | Required | The State Type (e.g. InitialState, AllStates, TerminalState, SelectedStates) |
| **SelectedStates** | **List&lt;string&gt;** | Optional | Named states for which the field will be readonly - This field can only be populated if StateType &#x3D; SelectedStates |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ReadOnlyStates(
    stateType: "...",  // required — The State Type (e.g. InitialState, AllStates, TerminalState, SelectedStates)
    selectedStates:   // optional — Named states for which the field will be readonly - This field can only be populated if StateType &#x3D; SelectedStates
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReadOnlyStates>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

