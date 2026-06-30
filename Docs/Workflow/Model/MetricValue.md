# Finbourne.Sdk.Workflow.Model.MetricValue

The numeric value of a metric property, with an optional unit.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **decimal** | Optional | The numerical value of the property. |
| **Unit** | **string** | Optional | The unit identifier for the value. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new MetricValue(
    value: 0.0d,  // optional — The numerical value of the property.
    unit: "..."  // optional — The unit identifier for the value.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MetricValue>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

