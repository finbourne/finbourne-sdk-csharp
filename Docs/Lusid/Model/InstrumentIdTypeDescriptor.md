# Finbourne.Sdk.Lusid.Model.InstrumentIdTypeDescriptor

The description of an allowable instrument identifier.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IdentifierType** | **string** | Required | The name of the identifier type. |
| **PropertyKey** | **string** | Required | The property key that corresponds to the identifier type. |
| **IsUniqueIdentifierType** | **bool** | Required | Whether or not the identifier type is enforced to be unique. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentIdTypeDescriptor(
    identifierType: "...",  // required — The name of the identifier type.
    propertyKey: "...",  // required — The property key that corresponds to the identifier type.
    isUniqueIdentifierType: true  // required — Whether or not the identifier type is enforced to be unique.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentIdTypeDescriptor>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

