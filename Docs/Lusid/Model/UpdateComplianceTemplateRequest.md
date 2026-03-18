# Finbourne.Sdk.Lusid.Model.UpdateComplianceTemplateRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code given for the Compliance Template |
| **Description** | **string** | Required | The description of the Compliance Template |
| **Variations** | [List&lt;ComplianceTemplateVariationRequest&gt;](ComplianceTemplateVariationRequest.md) | Required | Variation details of a Compliance Template |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateComplianceTemplateRequest(
    code: "...",  // required — The code given for the Compliance Template
    description: "...",  // required — The description of the Compliance Template
    variations: new List<ComplianceTemplateVariationRequest>()  // required — Variation details of a Compliance Template
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateComplianceTemplateRequest>(json);
```

- [ComplianceTemplateVariationRequest](ComplianceTemplateVariationRequest.md) — used in `Variations`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

