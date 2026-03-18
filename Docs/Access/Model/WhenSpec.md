# Finbourne.Sdk.Access.Model.WhenSpec

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Activate** | **DateTimeOffset** | Required | *No description available.* |
| **Deactivate** | **DateTimeOffset?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new WhenSpec(
    activate: DateTimeOffset.Now,  // required
    deactivate: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WhenSpec>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

