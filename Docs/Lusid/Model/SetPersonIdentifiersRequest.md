# Finbourne.Sdk.Lusid.Model.SetPersonIdentifiersRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Identifiers** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Identifiers to set for a Person. Identifiers not included in the request will not be amended. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SetPersonIdentifiersRequest(
    identifiers: new Property(...)  // optional — Identifiers to set for a Person. Identifiers not included in the request will not be amended.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SetPersonIdentifiersRequest>(json);
```


## Related Models

- [Property](Property.md) — used in `Identifiers`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

