# Finbourne.Sdk.Horizon.Model.OpenFigiPermIdResult

A packed WebAPI OpenFigi DTO and PermId DTO
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OpenFigiResult** | [OpenFigiData](OpenFigiData.md) | Required | *No description available.* |
| **PermIdResult** | [PermIdData](PermIdData.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new OpenFigiPermIdResult(
    openFigiResult: new OpenFigiData(...),  // required
    permIdResult: new PermIdData(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OpenFigiPermIdResult>(json);
```


## Related Models

- [OpenFigiData](OpenFigiData.md)
- [PermIdData](PermIdData.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

