# Finbourne.Sdk.Luminesce.Model.AccessControlledResourceIdentifierPartSchemaAttribute

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Index** | **int** | Optional | *No description available.* |
| **Name** | **string** | Optional | *No description available.* |
| **DisplayName** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **Required** | **bool** | Optional | *No description available.* |
| **ValuesPath** | **string** | Optional | *No description available.* |
| **TypeId** | **Object** | Optional | *No description available.* *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new AccessControlledResourceIdentifierPartSchemaAttribute(
    index: 0,  // optional
    name: "...",  // optional
    displayName: "...",  // optional
    description: "...",  // optional
    required: true,  // optional
    valuesPath: "...",  // optional
    typeId:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccessControlledResourceIdentifierPartSchemaAttribute>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

