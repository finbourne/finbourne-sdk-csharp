# Finbourne.Sdk.Lusid.Model.ResultDataSchema

The shape and type of the returned data. The AddressSchema gives information about the requested keys,  including the return type, links to further documentation, lifecycle status and removal date if they are  deprecated.                Note: the NodeValueSchema and PropertySchema fields have been deprecated. Please use the AddressSchema instead.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NodeValueSchema** | [Dictionary&lt;string, FieldSchema&gt;](FieldSchema.md) | Optional | This has been deprecated. Please use AddressSchema instead. |
| **PropertySchema** | [Dictionary&lt;string, FieldSchema&gt;](FieldSchema.md) | Optional | This has been deprecated. Please use AddressSchema instead. |
| **AddressSchema** | [Dictionary&lt;string, AddressDefinition&gt;](AddressDefinition.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResultDataSchema(
    nodeValueSchema: new FieldSchema(...),  // optional — This has been deprecated. Please use AddressSchema instead.
    propertySchema: new FieldSchema(...),  // optional — This has been deprecated. Please use AddressSchema instead.
    addressSchema: new AddressDefinition(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResultDataSchema>(json);
```


## Related Models

- [FieldSchema](FieldSchema.md) — used in `NodeValueSchema`
- [FieldSchema](FieldSchema.md) — used in `PropertySchema`
- [AddressDefinition](AddressDefinition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

