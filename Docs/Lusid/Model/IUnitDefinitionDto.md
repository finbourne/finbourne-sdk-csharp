# Finbourne.Sdk.Lusid.Model.IUnitDefinitionDto

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Schema** | **string** | Optional | The available values are: NoUnits, Basic, Iso4217Currency |
| **Code** | **string** | Optional | *No description available.* *(read-only)* |
| **DisplayName** | **string** | Optional | *No description available.* *(read-only)* |
| **Description** | **string** | Optional | *No description available.* *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IUnitDefinitionDto(
    schema: "...",  // optional — The available values are: NoUnits, Basic, Iso4217Currency
    code: "...",  // optional
    displayName: "...",  // optional
    description: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IUnitDefinitionDto>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

