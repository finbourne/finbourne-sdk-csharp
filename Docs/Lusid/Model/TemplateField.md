# Finbourne.Sdk.Lusid.Model.TemplateField

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FieldName** | **string** | Required | *No description available.* |
| **Specificity** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **Type** | **string** | Required | *No description available.* |
| **Availability** | **string** | Required | *No description available.* |
| **Usage** | **List&lt;string&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TemplateField(
    fieldName: "...",  // required
    specificity: "...",  // required
    description: "...",  // required
    type: "...",  // required
    availability: "...",  // required
    usage:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TemplateField>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

