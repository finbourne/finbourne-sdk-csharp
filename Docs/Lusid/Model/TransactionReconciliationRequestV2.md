# Finbourne.Sdk.Lusid.Model.TransactionReconciliationRequestV2

Specification for the reconciliation request. Left and Right hand sides are constructed. Each consists of transactions from a portfolio  The results of this can then be compared to each other.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [AggregatedTransactionsRequest](AggregatedTransactionsRequest.md) | Required | *No description available.* |
| **Right** | [AggregatedTransactionsRequest](AggregatedTransactionsRequest.md) | Required | *No description available.* |
| **LeftToRightMapping** | [List&lt;ReconciliationLeftRightAddressKeyPair&gt;](ReconciliationLeftRightAddressKeyPair.md) | Optional | The mapping from property keys requested by left aggregation to property keys on right hand side |
| **ComparisonRules** | [List&lt;ReconciliationRule&gt;](ReconciliationRule.md) | Optional | The set of rules to be used in comparing values. These are the rules that determine what constitutes a match.  The simplest is obviously an exact one-for-one comparison, but tolerances on numerical or date time values and  case-insensitive string comparison are supported amongst other types. |
| **PreserveKeys** | **List&lt;string&gt;** | Optional | List of keys to preserve (from rhs) in the diff. Used in conjunction with filtering/grouping.  If two values are equal, for a given key then the value is elided from the results. Setting it here  will preserve it (takes the values from the RHS and puts it into the line by line results). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionReconciliationRequestV2(
    left: new AggregatedTransactionsRequest(...),  // required
    right: new AggregatedTransactionsRequest(...),  // required
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
var instance = JsonConvert.DeserializeObject<TransactionReconciliationRequestV2>(json);
```


## Related Models

- [AggregatedTransactionsRequest](AggregatedTransactionsRequest.md)
- [AggregatedTransactionsRequest](AggregatedTransactionsRequest.md)
- [ReconciliationLeftRightAddressKeyPair](ReconciliationLeftRightAddressKeyPair.md) — used in `LeftToRightMapping`
- [ReconciliationRule](ReconciliationRule.md) — used in `ComparisonRules`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

