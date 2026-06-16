# Finbourne.Sdk.Lusid.Model.UpsertAddressKeyAliasRequest

A request to upsert an address key alias.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AddressKeyAlias** | [AddressKeyAlias](AddressKeyAlias.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertAddressKeyAliasRequest(
    addressKeyAlias: new AddressKeyAlias(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertAddressKeyAliasRequest>(json);
```


## Related Models

- [AddressKeyAlias](AddressKeyAlias.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

