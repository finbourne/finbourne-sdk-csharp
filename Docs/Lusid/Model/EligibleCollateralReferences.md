# Finbourne.Sdk.Lusid.Model.EligibleCollateralReferences

The eligible collateral schedule each party's posting is checked against.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WePost** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TheyPost** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EligibleCollateralReferences(
    wePost: new ResourceId(...),  // optional
    theyPost: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EligibleCollateralReferences>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

