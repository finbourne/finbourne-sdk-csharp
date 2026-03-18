# Finbourne.Sdk.Lusid.Model.FeeTransactionTemplateSpecification

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SpecificationTypeName** | **string** | Required | *No description available.* |
| **SupportedTemplateFields** | [List&lt;TemplateField&gt;](TemplateField.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeTransactionTemplateSpecification(
    specificationTypeName: "...",  // required
    supportedTemplateFields: new List<TemplateField>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeeTransactionTemplateSpecification>(json);
```

- [TemplateField](TemplateField.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

