# Finbourne.Sdk.Luminesce.Model.ExportColumnColor

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Preset** | **string** | Optional | *No description available.* |
| **Hex** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ExportColumnColor(
    preset: "...",  // optional
    hex: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExportColumnColor>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

