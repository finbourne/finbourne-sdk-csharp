# Finbourne.Sdk.Lusid.Model.GetAddressKeyAliasResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | *No description available.* |
| **Value** | [AddressKeyAlias](AddressKeyAlias.md) | Optional | *No description available.* |
| **Failed** | [ErrorDetail](ErrorDetail.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GetAddressKeyAliasResponse(
    href: "...",  // optional
    value: new AddressKeyAlias(...),  // optional
    failed: new ErrorDetail(...),  // optional
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
- [ErrorDetail](ErrorDetail.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

