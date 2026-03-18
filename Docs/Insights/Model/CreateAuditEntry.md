# Finbourne.Sdk.Insights.Model.CreateAuditEntry

Details to create an audit entry
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Process** | [AuditProcess](AuditProcess.md) | Required | *No description available.* |
| **Data** | [AuditData](AuditData.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new CreateAuditEntry(
    process: new AuditProcess(...),  // required
    data: new AuditData(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateAuditEntry>(json);
```


## Related Models

- [AuditProcess](AuditProcess.md)
- [AuditData](AuditData.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

