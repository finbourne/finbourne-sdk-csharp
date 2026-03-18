# Finbourne.Sdk.Lusid.Model.UpsertDialectRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [DialectId](DialectId.md) | Required | *No description available.* |
| **Schema** | [DialectSchema](DialectSchema.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertDialectRequest(
    id: new DialectId(...),  // required
    schema: new DialectSchema(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertDialectRequest>(json);
```


## Related Models

- [DialectId](DialectId.md)
- [DialectSchema](DialectSchema.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

