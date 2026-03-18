# Finbourne.Sdk.Insights.Model.AuditEntry

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | *No description available.* |
| **Date** | **DateTimeOffset** | Required | *No description available.* |
| **Process** | [AuditProcess](AuditProcess.md) | Required | *No description available.* |
| **Data** | [AuditData](AuditData.md) | Required | *No description available.* |
| **Notes** | [List&lt;AuditEntryNote&gt;](AuditEntryNote.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new AuditEntry(
    id: "...",  // required
    date: DateTimeOffset.Now,  // required
    process: new AuditProcess(...),  // required
    data: new AuditData(...),  // required
    notes: new List<AuditEntryNote>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AuditEntry>(json);
```

- [AuditProcess](AuditProcess.md)
- [AuditData](AuditData.md)
- [AuditEntryNote](AuditEntryNote.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

