# Finbourne.Sdk.Access.Model.EffectiveRange

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **From** | **DateTimeOffset** | Optional | *No description available.* |
| **To** | **DateTimeOffset?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new EffectiveRange(
    from: DateTimeOffset.Now,  // optional
    to: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EffectiveRange>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

