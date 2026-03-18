# Finbourne.Sdk.Lusid.Model.UpsertComplianceRunSummaryResult

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InstigatedAt** | **DateTimeOffset** | Required | *No description available.* |
| **CompletedAt** | **DateTimeOffset** | Required | *No description available.* |
| **Schedule** | **string** | Required | *No description available.* |
| **Results** | [List&lt;ComplianceSummaryRuleResult&gt;](ComplianceSummaryRuleResult.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertComplianceRunSummaryResult(
    runId: new ResourceId(...),  // required
    instigatedAt: DateTimeOffset.Now,  // required
    completedAt: DateTimeOffset.Now,  // required
    schedule: "...",  // required
    results: new List<ComplianceSummaryRuleResult>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertComplianceRunSummaryResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ComplianceSummaryRuleResult](ComplianceSummaryRuleResult.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

