# Finbourne.Sdk.Lusid.Model.ComplianceComparisonOperand

One side of a comparison: the sub-expression that produced it and, where the group carried the data to evaluate it,  its value. The value is absent for a non-numeric constant, a reference list, or an operand the group held no data for.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Expression** | **string** | Required | *No description available.* |
| **Value** | **decimal?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceComparisonOperand(
    expression: "...",  // required
    value: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceComparisonOperand>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

