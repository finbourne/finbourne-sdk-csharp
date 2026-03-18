# Finbourne.Sdk.Lusid.Model.DecoratedComplianceRunSummary

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Details** | [List&lt;ComplianceRuleResultDetail&gt;](ComplianceRuleResultDetail.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DecoratedComplianceRunSummary(
    runId: new ResourceId(...),  // required
    details: new List<ComplianceRuleResultDetail>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DecoratedComplianceRunSummary>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ComplianceRuleResultDetail](ComplianceRuleResultDetail.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

