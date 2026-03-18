# Finbourne.Sdk.Lusid.Model.ReconciliationLine

In evaluating a left and right hand side holding or valuation set, two data records result. These are then compared based on a set of  rules. This results in either a match or failure to match. If there is a match both left and right will be present, otherwise one will not.  A difference will be present if a match was calculated.  The options used in comparison may result in elision of results where an exact or tolerable match is made.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **Dictionary&lt;string, Object&gt;** | Optional | Left hand side of the comparison |
| **Right** | **Dictionary&lt;string, Object&gt;** | Optional | Right hand side of the comparison |
| **Difference** | **Dictionary&lt;string, Object&gt;** | Optional | Difference between LHS and RHS of comparison |
| **ResultComparison** | **Dictionary&lt;string, Object&gt;** | Optional | The logical or semantic description of the difference, e.g. \&quot;Matches\&quot; or \&quot;MatchesWithTolerance\&quot; or \&quot;Failed\&quot;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconciliationLine(
    left: ,  // optional — Left hand side of the comparison
    right: ,  // optional — Right hand side of the comparison
    difference: ,  // optional — Difference between LHS and RHS of comparison
    resultComparison:   // optional — The logical or semantic description of the difference, e.g. \&quot;Matches\&quot; or \&quot;MatchesWithTolerance\&quot; or \&quot;Failed\&quot;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReconciliationLine>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

