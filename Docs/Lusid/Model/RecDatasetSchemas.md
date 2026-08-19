# Finbourne.Sdk.Lusid.Model.RecDatasetSchemas

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [RecDatasetSchema](RecDatasetSchema.md) | Optional | *No description available.* |
| **Right** | [RecDatasetSchema](RecDatasetSchema.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDatasetSchemas(
    left: new RecDatasetSchema(...),  // optional
    right: new RecDatasetSchema(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecDatasetSchemas>(json);
```


## Related Models

- [RecDatasetSchema](RecDatasetSchema.md)
- [RecDatasetSchema](RecDatasetSchema.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

