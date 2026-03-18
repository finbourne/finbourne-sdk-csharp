# Finbourne.Sdk.Lusid.Model.UpdatePropertyDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The display name of the property. |
| **PropertyDescription** | **string** | Optional | Describes the property |
| **CustomEntityTypes** | **List&lt;string&gt;** | Optional | The custom entity types that properties relating to this property definition can be applied to. |
| **ValueFormat** | **string** | Optional | The format in which values for this property definition should be represented. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdatePropertyDefinitionRequest(
    displayName: "...",  // required — The display name of the property.
    propertyDescription: "...",  // optional — Describes the property
    customEntityTypes: ,  // optional — The custom entity types that properties relating to this property definition can be applied to.
    valueFormat: "..."  // optional — The format in which values for this property definition should be represented.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdatePropertyDefinitionRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

