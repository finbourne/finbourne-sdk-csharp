# Finbourne.Sdk.Lusid.Model.UpsertComplianceRunSummaryRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InstigatedAt** | **DateTimeOffset** | Required | *No description available.* |
| **CompletedAt** | **DateTimeOffset** | Required | *No description available.* |
| **Schedule** | **string** | Required | *No description available.* |
| **Results** | [List&lt;ComplianceSummaryRuleResultRequest&gt;](ComplianceSummaryRuleResultRequest.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertComplianceRunSummaryRequest(
    runId: new ResourceId(...),  // required
    instigatedAt: DateTimeOffset.Now,  // required
    completedAt: DateTimeOffset.Now,  // required
    schedule: "...",  // required
    results: new List<ComplianceSummaryRuleResultRequest>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertComplianceRunSummaryRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ComplianceSummaryRuleResultRequest](ComplianceSummaryRuleResultRequest.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

