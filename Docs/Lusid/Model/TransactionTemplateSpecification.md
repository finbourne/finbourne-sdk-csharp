# Finbourne.Sdk.Lusid.Model.TransactionTemplateSpecification

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentEventType** | **string** | Required | *No description available.* |
| **SupportedInstrumentTypes** | **List&lt;string&gt;** | Required | *No description available.* |
| **SupportedParticipationTypes** | **List&lt;string&gt;** | Required | *No description available.* |
| **SupportedElectionTypes** | [List&lt;ElectionSpecification&gt;](ElectionSpecification.md) | Required | *No description available.* |
| **SupportedTemplateFields** | [List&lt;TemplateField&gt;](TemplateField.md) | Required | *No description available.* |
| **EligibilityCalculation** | [EligibilityCalculation](EligibilityCalculation.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionTemplateSpecification(
    instrumentEventType: "...",  // required
    supportedInstrumentTypes: ,  // required
    supportedParticipationTypes: ,  // required
    supportedElectionTypes: new List<ElectionSpecification>(),  // required
    supportedTemplateFields: new List<TemplateField>(),  // required
    eligibilityCalculation: new EligibilityCalculation(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionTemplateSpecification>(json);
```

- [ElectionSpecification](ElectionSpecification.md)
- [TemplateField](TemplateField.md)
- [EligibilityCalculation](EligibilityCalculation.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

