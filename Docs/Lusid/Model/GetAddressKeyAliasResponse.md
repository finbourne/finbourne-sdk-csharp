# Finbourne.Sdk.Lusid.Model.GetAddressKeyAliasResponse

The response to a singular address key alias read. There is deliberately no failure block on this  type: every route returning it is a singular (or list-of-singular) read, never a batch keyed  lookup, so there is no per-key error to report - an invalid entity is rejected at upsert and  a failed read fails the whole request. The IGetResponse batch members below throw for the  same reason; do not reintroduce a Failed property when copying this shape.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | *No description available.* |
| **Value** | [AddressKeyAlias](AddressKeyAlias.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GetAddressKeyAliasResponse(
    href: "...",  // optional
    value: new AddressKeyAlias(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GetAddressKeyAliasResponse>(json);
```

- [AddressKeyAlias](AddressKeyAlias.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

