# Finbourne.Sdk.Lusid.Model.EntityIdentifier

Dto to expose mapped keys to new standardised format
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IdentifierScope** | **string** | Optional | The scope of the identifier |
| **IdentifierType** | **string** | Required | The type of the identifier |
| **IdentifierValue** | **string** | Required | The value of the identifier |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EntityIdentifier(
    identifierScope: "...",  // optional — The scope of the identifier
    identifierType: "...",  // required — The type of the identifier
    identifierValue: "..."  // required — The value of the identifier
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EntityIdentifier>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

