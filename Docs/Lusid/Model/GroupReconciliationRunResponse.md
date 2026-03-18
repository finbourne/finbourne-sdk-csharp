# Finbourne.Sdk.Lusid.Model.GroupReconciliationRunResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ReconciliationSummaries** | [List&lt;GroupReconciliationSummary&gt;](GroupReconciliationSummary.md) | Required | One summary record for each of the \&quot;Holding\&quot; | \&quot;Transaction\&quot; | \&quot;Valuation\&quot; reconciliations performed |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationRunResponse(
    reconciliationSummaries: new List<GroupReconciliationSummary>()  // required — One summary record for each of the \&quot;Holding\&quot; | \&quot;Transaction\&quot; | \&quot;Valuation\&quot; reconciliations performed
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationRunResponse>(json);
```


## Related Models

- [GroupReconciliationSummary](GroupReconciliationSummary.md) — used in `ReconciliationSummaries`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

