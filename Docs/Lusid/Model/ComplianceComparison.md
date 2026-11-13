# Finbourne.Sdk.Lusid.Model.ComplianceComparison

A single leaf comparison the check criterion made, re-evaluated for this group. A result of null is a comparison the  group held no data for (the criterion short-circuited past it).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Predicate** | **string** | Required | *No description available.* |
| **Left** | [ComplianceComparisonOperand](ComplianceComparisonOperand.md) | Required | *No description available.* |
| **Operator** | **string** | Required | *No description available.* |
| **Right** | [ComplianceComparisonOperand](ComplianceComparisonOperand.md) | Required | *No description available.* |
| **Passed** | **bool?** | Optional | Whether this leaf met its criterion for the group: true where it held, false for a breaching leaf. Absent for a  comparison the group carried no data for (the criterion short-circuited past it). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceComparison(
    predicate: "...",  // required
    left: new ComplianceComparisonOperand(...),  // required
    varOperator: "...",  // required
    right: new ComplianceComparisonOperand(...),  // required
    passed: true  // optional — Whether this leaf met its criterion for the group: true where it held, false for a breaching leaf. Absent for a  comparison the group carried no data for (the criterion short-circuited past it).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceComparison>(json);
```

- [ComplianceComparisonOperand](ComplianceComparisonOperand.md)
- [ComplianceComparisonOperand](ComplianceComparisonOperand.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

