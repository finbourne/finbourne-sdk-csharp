# Finbourne.Sdk.Horizon.Model.LusidPropertyDefinitionOverrides

Override values for property Display Name and Description
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayNameOverride** | **string** | Optional | *No description available.* |
| **DescriptionOverride** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new LusidPropertyDefinitionOverrides(
    displayNameOverride: "...",  // optional
    descriptionOverride: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidPropertyDefinitionOverrides>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

