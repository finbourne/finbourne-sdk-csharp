# Finbourne.Sdk.Horizon.Model.LusidPropertyDefinition

Defines the information in a LUSID Property Definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | *No description available.* *(read-only)* |
| **ProductEntityItemKey** | **string** | Required | Property key associated with the mapping |
| **Domain** | **string** | Required | The domain of this definition. |
| **Scope** | **string** | Required | The scope of this definition. |
| **Code** | **string** | Required | The code of this definition. |
| **DisplayName** | **string** | Required | The name used when this definition is displayed. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **Lifetime** | **string** | Required | *No description available.* |
| **ConstraintStyle** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new LusidPropertyDefinition(
    key: "...",  // required
    productEntityItemKey: "...",  // required — Property key associated with the mapping
    domain: "...",  // required — The domain of this definition.
    scope: "...",  // required — The scope of this definition.
    code: "...",  // required — The code of this definition.
    displayName: "...",  // required — The name used when this definition is displayed.
    dataTypeId: new ResourceId(...),  // required
    description: "...",  // required
    lifetime: "...",  // required
    constraintStyle: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidPropertyDefinition>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

