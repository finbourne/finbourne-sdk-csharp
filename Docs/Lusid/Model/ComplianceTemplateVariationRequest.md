# Finbourne.Sdk.Lusid.Model.ComplianceTemplateVariationRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Label** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **OutcomeDescription** | **string** | Optional | *No description available.* |
| **ReferencedGroupLabel** | **string** | Optional | *No description available.* |
| **Steps** | [List&lt;ComplianceStepRequest&gt;](ComplianceStepRequest.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceTemplateVariationRequest(
    label: "...",  // required
    description: "...",  // required
    outcomeDescription: "...",  // optional
    referencedGroupLabel: "...",  // optional
    steps: new List<ComplianceStepRequest>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceTemplateVariationRequest>(json);
```

- [ComplianceStepRequest](ComplianceStepRequest.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

