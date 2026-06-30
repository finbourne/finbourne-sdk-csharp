# Finbourne.Sdk.Workflow.Model.PropertyValue

The value of a property. Exactly one of Finbourne.Workflow.WebApi.Common.Dto.Json.Properties.PropertyValue.LabelValue, Finbourne.Workflow.WebApi.Common.Dto.Json.Properties.PropertyValue.MetricValue or Finbourne.Workflow.WebApi.Common.Dto.Json.Properties.PropertyValue.LabelValueSet should be supplied.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LabelValue** | **string** | Optional | The value of a text property. |
| **MetricValue** | [MetricValue](MetricValue.md) | Optional | *No description available.* |
| **LabelValueSet** | [LabelValueSet](LabelValueSet.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new PropertyValue(
    labelValue: "...",  // optional — The value of a text property.
    metricValue: new MetricValue(...),  // optional
    labelValueSet: new LabelValueSet(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PropertyValue>(json);
```

- [MetricValue](MetricValue.md)
- [LabelValueSet](LabelValueSet.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

