# Finbourne.Sdk.Lusid.Model.ReconciliationRequest

Specification for the reconciliation request. Left and Right hand sides are constructed. Each consists of a valuation of a portfolio  using an aggregation request. The results of this can then be compared to each other. The difference, which is effectively a risk based  difference allows comparison of the effects of changing a recipe, valuation date, or (though it may or may not make logical sense) a portfolio.  For instance, one might look at the difference in risk caused by the addition of transaction to a portfolio, or through changing the valuation  methodology or system.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [ValuationRequest](ValuationRequest.md) | Required | *No description available.* |
| **Right** | [ValuationRequest](ValuationRequest.md) | Required | *No description available.* |
| **LeftToRightMapping** | [List&lt;ReconciliationLeftRightAddressKeyPair&gt;](ReconciliationLeftRightAddressKeyPair.md) | Optional | The mapping from property keys requested by left aggregation to property keys on right hand side |
| **ComparisonRules** | [List&lt;ReconciliationRule&gt;](ReconciliationRule.md) | Optional | The set of rules to be used in comparing values. These are the rules that determine what constitutes a match.  The simplest is obviously an exact one-for-one comparison, but tolerances on numerical or date time values and  case-insensitive string comparison are supported amongst other types. |
| **PreserveKeys** | **List&lt;string&gt;** | Optional | List of keys to preserve (from rhs) in the diff. Used in conjunction with filtering/grouping.  If two values are equal, for a given key then the value is elided from the results. Setting it here  will preserve it (takes the values from the RHS and puts it into the line by line results). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconciliationRequest(
    left: new ValuationRequest(...),  // required
    right: new ValuationRequest(...),  // required
    leftToRightMapping: new List<ReconciliationLeftRightAddressKeyPair>(),  // optional — The mapping from property keys requested by left aggregation to property keys on right hand side
    comparisonRules: new List<ReconciliationRule>(),  // optional — The set of rules to be used in comparing values. These are the rules that determine what constitutes a match.  The simplest is obviously an exact one-for-one comparison, but tolerances on numerical or date time values and  case-insensitive string comparison are supported amongst other types.
    preserveKeys:   // optional — List of keys to preserve (from rhs) in the diff. Used in conjunction with filtering/grouping.  If two values are equal, for a given key then the value is elided from the results. Setting it here  will preserve it (takes the values from the RHS and puts it into the line by line results).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReconciliationRequest>(json);
```


## Related Models

- [ValuationRequest](ValuationRequest.md)
- [ValuationRequest](ValuationRequest.md)
- [ReconciliationLeftRightAddressKeyPair](ReconciliationLeftRightAddressKeyPair.md) — used in `LeftToRightMapping`
- [ReconciliationRule](ReconciliationRule.md) — used in `ComparisonRules`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

