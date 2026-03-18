# Finbourne.Sdk.Lusid.Model.PropertyValue

The value of the property.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LabelValue** | **string** | Optional | The text value of a property defined as having the &#39;Label&#39; type. |
| **MetricValue** | [MetricValue](MetricValue.md) | Optional | *No description available.* |
| **LabelValueSet** | [LabelValueSet](LabelValueSet.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PropertyValue(
    labelValue: "...",  // optional — The text value of a property defined as having the &#39;Label&#39; type.
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

