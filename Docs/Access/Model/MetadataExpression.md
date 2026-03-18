# Finbourne.Sdk.Access.Model.MetadataExpression

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MetadataKey** | **string** | Required | *No description available.* |
| **Operator** | **Operator** | Required | *No description available.* |
| **TextValue** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new MetadataExpression(
    metadataKey: "...",  // required
    varOperator: ,  // required
    textValue: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MetadataExpression>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

