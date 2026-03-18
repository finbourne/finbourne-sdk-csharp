# Finbourne.Sdk.Insights.Model.AuditProcessSummary

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Process** | [AuditProcess](AuditProcess.md) | Optional | *No description available.* |
| **LatestEntry** | [AuditData](AuditData.md) | Optional | *No description available.* |
| **Summary** | [AuditDataSummary](AuditDataSummary.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new AuditProcessSummary(
    process: new AuditProcess(...),  // optional
    latestEntry: new AuditData(...),  // optional
    summary: new AuditDataSummary(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AuditProcessSummary>(json);
```


## Related Models

- [AuditProcess](AuditProcess.md)
- [AuditData](AuditData.md)
- [AuditDataSummary](AuditDataSummary.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

