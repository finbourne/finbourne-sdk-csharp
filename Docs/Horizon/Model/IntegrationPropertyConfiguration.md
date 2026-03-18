# Finbourne.Sdk.Horizon.Model.IntegrationPropertyConfiguration

Response containing the description of an integration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The Integration this property configuration applies to |
| **Properties** | [List&lt;PropertyMapping&gt;](PropertyMapping.md) | Required | The mandatory and optional properties available in this integration |
| **Fields** | [List&lt;FieldMapping&gt;](FieldMapping.md) | Required | The fields available in this integration |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationPropertyConfiguration(
    type: "...",  // required — The Integration this property configuration applies to
    properties: new List<PropertyMapping>(),  // required — The mandatory and optional properties available in this integration
    fields: new List<FieldMapping>()  // required — The fields available in this integration
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationPropertyConfiguration>(json);
```

- [PropertyMapping](PropertyMapping.md) — used in `Properties`
- [FieldMapping](FieldMapping.md) — used in `Fields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

