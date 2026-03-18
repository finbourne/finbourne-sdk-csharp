# Finbourne.Sdk.Lusid.Model.Dialect

The language/format of a translatable entity. Entities can be LUSID native or external and the Dialect describes  1) the system that understands the entity and  2) applicable validation for the entity, in the form of a schema.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [DialectId](DialectId.md) | Required | *No description available.* |
| **Schema** | [DialectSchema](DialectSchema.md) | Required | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Dialect(
    id: new DialectId(...),  // required
    schema: new DialectSchema(...),  // required
    varVersion: new ModelVersion(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Dialect>(json);
```


## Related Models

- [DialectId](DialectId.md)
- [DialectSchema](DialectSchema.md)
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

