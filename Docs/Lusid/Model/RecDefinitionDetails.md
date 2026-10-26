# Finbourne.Sdk.Lusid.Model.RecDefinitionDetails

Base class for the part of a rec definition whose shape depends on what it reconciles. Polymorphic by  definitionType; each supported type has a corresponding inherited class.

## oneOf Type

`RecDefinitionDetails` can be one of the following types:

* [ExternalRecDefinitionDetails](./ExternalRecDefinitionDetails.md)
* [LusidEntityRecDefinitionDetails](./LusidEntityRecDefinitionDetails.md)
* [PortfolioContentsRecDefinitionDetails](./PortfolioContentsRecDefinitionDetails.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var inner = new ExternalRecDefinitionDetails(...);
var instance = new RecDefinitionDetails(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecDefinitionDetails>(json);
```

## Related Models

- [ExternalRecDefinitionDetails](./ExternalRecDefinitionDetails.md)
- [LusidEntityRecDefinitionDetails](./LusidEntityRecDefinitionDetails.md)
- [PortfolioContentsRecDefinitionDetails](./PortfolioContentsRecDefinitionDetails.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

