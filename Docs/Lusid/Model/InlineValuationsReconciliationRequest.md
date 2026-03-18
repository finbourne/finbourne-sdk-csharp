# Finbourne.Sdk.Lusid.Model.InlineValuationsReconciliationRequest

Specification for the reconciliation request. Left and Right hand sides are constructed. Each consists of a valuation of a inline set of instruments  using an inline aggregation request. The results of this can then be compared to each other. The difference, which is effectively a risk based  difference allows comparison of the effects of changing a recipe, valuation date, or (though it may or may not make logical sense) a set of instruments.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [InlineValuationRequest](InlineValuationRequest.md) | Required | *No description available.* |
| **Right** | [InlineValuationRequest](InlineValuationRequest.md) | Required | *No description available.* |
| **LeftToRightMapping** | [List&lt;ReconciliationLeftRightAddressKeyPair&gt;](ReconciliationLeftRightAddressKeyPair.md) | Optional | The mapping from property keys requested by left aggregation to property keys on right hand side |
| **PreserveKeys** | **List&lt;string&gt;** | Optional | List of keys to preserve (from rhs) in the diff. Used in conjunction with filtering/grouping |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InlineValuationsReconciliationRequest(
    left: new InlineValuationRequest(...),  // required
    right: new InlineValuationRequest(...),  // required
    leftToRightMapping: new List<ReconciliationLeftRightAddressKeyPair>(),  // optional — The mapping from property keys requested by left aggregation to property keys on right hand side
    preserveKeys:   // optional — List of keys to preserve (from rhs) in the diff. Used in conjunction with filtering/grouping
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InlineValuationsReconciliationRequest>(json);
```


## Related Models

- [InlineValuationRequest](InlineValuationRequest.md)
- [InlineValuationRequest](InlineValuationRequest.md)
- [ReconciliationLeftRightAddressKeyPair](ReconciliationLeftRightAddressKeyPair.md) — used in `LeftToRightMapping`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

