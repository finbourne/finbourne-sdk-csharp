# Finbourne.Sdk.Luminesce.Model.MappableField

Information about a field that can be designed on (regardless if it currently is) Kind of a \"mini-available catalog entry\"
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | Name of the field in need of mapping (The field name from within the Table Parameter itself) |
| **Type** | **DataType** | Optional | *No description available.* |
| **Description** | **string** | Optional | Description of the field (just for rendering to the user) |
| **DisplayName** | **string** | Optional | Display Name of the field (just for rendering to the user) |
| **SampleValues** | **string** | Optional | Example values for the field (just for rendering to the user) |
| **AllowedValues** | **string** | Optional | Any set of exactly allowed values for the field (perhaps just for rendering to the user, if nothing else) |
| **MandatoryForActions** | **string** | Optional | Which &#x60;Actions&#x60; is this mandatory for? If any (and potentially when), perhaps just for rendering to the user, if nothing else |
| **Mapping** | [ExpressionWithAlias](ExpressionWithAlias.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new MappableField(
    name: "...",  // optional — Name of the field in need of mapping (The field name from within the Table Parameter itself)
    type: ,  // optional
    description: "...",  // optional — Description of the field (just for rendering to the user)
    displayName: "...",  // optional — Display Name of the field (just for rendering to the user)
    sampleValues: "...",  // optional — Example values for the field (just for rendering to the user)
    allowedValues: "...",  // optional — Any set of exactly allowed values for the field (perhaps just for rendering to the user, if nothing else)
    mandatoryForActions: "...",  // optional — Which &#x60;Actions&#x60; is this mandatory for? If any (and potentially when), perhaps just for rendering to the user, if nothing else
    mapping: new ExpressionWithAlias(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MappableField>(json);
```

- [ExpressionWithAlias](ExpressionWithAlias.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

