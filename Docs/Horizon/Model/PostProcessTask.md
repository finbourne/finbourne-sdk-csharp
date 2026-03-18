# Finbourne.Sdk.Horizon.Model.PostProcessTask

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Action** | **string** | Required | *No description available.* |
| **TargetInstance** | **string** | Optional | *No description available.* |
| **TriggerOn** | **string** | Required | *No description available.* |
| **Parameters** | **Object** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new PostProcessTask(
    action: "...",  // required
    targetInstance: "...",  // optional
    triggerOn: "...",  // required
    parameters:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PostProcessTask>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

