# Finbourne.Sdk.Lusid.Model.ComplianceTemplateVariation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Label** | **string** | Required | Label of a Compliance Template Variation |
| **Description** | **string** | Required | The description of the Compliance Template Variation |
| **RequiredParameters** | [List&lt;ComplianceTemplateParameter&gt;](ComplianceTemplateParameter.md) | Required | A parameter required by a Compliance Template Variation |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Required | Properties associated with the Compliance Template Variation |
| **AcceptedAddressKeys** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Steps** | [List&lt;ComplianceStep&gt;](ComplianceStep.md) | Required | The steps expressed in this template, with their required parameters |
| **ReferencedGroupLabel** | **string** | Optional | The label of a given referenced group in a Compliance Rule Template Variation |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceTemplateVariation(
    label: "...",  // required — Label of a Compliance Template Variation
    description: "...",  // required — The description of the Compliance Template Variation
    requiredParameters: new List<ComplianceTemplateParameter>(),  // required — A parameter required by a Compliance Template Variation
    properties: new PerpetualProperty(...),  // required — Properties associated with the Compliance Template Variation
    acceptedAddressKeys: new ResourceId(...),  // required
    steps: new List<ComplianceStep>(),  // required — The steps expressed in this template, with their required parameters
    referencedGroupLabel: "..."  // optional — The label of a given referenced group in a Compliance Rule Template Variation
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceTemplateVariation>(json);
```

- [ComplianceTemplateParameter](ComplianceTemplateParameter.md) — used in `RequiredParameters`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [ResourceId](ResourceId.md)
- [ComplianceStep](ComplianceStep.md) — used in `Steps`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

