# Finbourne.Sdk.Lusid.Model.AddressKeyDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AddressKey** | **string** | Required | The address key of the address key definition. |
| **Type** | **string** | Required | The type of the address key definition |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AddressKeyDefinition(
    addressKey: "...",  // required — The address key of the address key definition.
    type: "...",  // required — The type of the address key definition
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AddressKeyDefinition>(json);
```

- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

