# Finbourne.Sdk.Lusid.Model.ReferenceData

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FieldDefinitions** | [List&lt;FieldDefinition&gt;](FieldDefinition.md) | Required | *No description available.* |
| **Values** | [List&lt;FieldValue&gt;](FieldValue.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReferenceData(
    fieldDefinitions: new List<FieldDefinition>(),  // required
    values: new List<FieldValue>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReferenceData>(json);
```


## Related Models

- [FieldDefinition](FieldDefinition.md)
- [FieldValue](FieldValue.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

