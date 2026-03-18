# Finbourne.Sdk.Insights.Model.AuditEntryNote

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UserId** | **string** | Required | *No description available.* |
| **Text** | **string** | Required | *No description available.* |
| **Date** | **DateTimeOffset** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new AuditEntryNote(
    userId: "...",  // required
    text: "...",  // required
    date: DateTimeOffset.Now  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AuditEntryNote>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

