# Finbourne.Sdk.Workflow.Model.LabelValueSet

The set of string labels that make up a multi-value property.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | **List&lt;string&gt;** | Required | The distinct string values of the multi-value property. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LabelValueSet(
    values:   // required — The distinct string values of the multi-value property.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LabelValueSet>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

