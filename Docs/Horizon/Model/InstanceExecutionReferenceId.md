# Finbourne.Sdk.Horizon.Model.InstanceExecutionReferenceId

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **Guid** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new InstanceExecutionReferenceId(
    value: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstanceExecutionReferenceId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

