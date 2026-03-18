# Finbourne.Sdk.Lusid.Model.ComplianceTemplate

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Description** | **string** | Required | The description of the Compliance Template |
| **Tags** | **List&lt;string&gt;** | Optional | Tags for a Compliance Template |
| **Variations** | [List&lt;ComplianceTemplateVariation&gt;](ComplianceTemplateVariation.md) | Required | Variation details of a Compliance Template |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceTemplate(
    id: new ResourceId(...),  // required
    description: "...",  // required — The description of the Compliance Template
    tags: ,  // optional — Tags for a Compliance Template
    variations: new List<ComplianceTemplateVariation>(),  // required — Variation details of a Compliance Template
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceTemplate>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ComplianceTemplateVariation](ComplianceTemplateVariation.md) — used in `Variations`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

