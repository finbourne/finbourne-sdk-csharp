# Finbourne.Sdk.Insights.Model.ScrollableCollectionOfAuditEntry

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Data** | [List&lt;AuditEntry&gt;](AuditEntry.md) | Optional | *No description available.* |
| **State** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new ScrollableCollectionOfAuditEntry(
    data: new List<AuditEntry>(),  // optional
    state: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScrollableCollectionOfAuditEntry>(json);
```


## Related Models

- [AuditEntry](AuditEntry.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

