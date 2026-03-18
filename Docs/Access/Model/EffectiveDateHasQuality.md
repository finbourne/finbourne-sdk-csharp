# Finbourne.Sdk.Access.Model.EffectiveDateHasQuality

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Quality** | **DateQuality** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new EffectiveDateHasQuality(
    quality:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EffectiveDateHasQuality>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

