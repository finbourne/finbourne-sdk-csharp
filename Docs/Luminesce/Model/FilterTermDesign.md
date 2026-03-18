# Finbourne.Sdk.Luminesce.Model.FilterTermDesign

A single filter clause
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Operator** | **QueryDesignerBinaryOperator** | Required | *No description available.* |
| **Value** | **string** | Required | The value to compare against (always as a string, but will be formatted to the correct type) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new FilterTermDesign(
    varOperator: ,  // required
    value: "..."  // required — The value to compare against (always as a string, but will be formatted to the correct type)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FilterTermDesign>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

