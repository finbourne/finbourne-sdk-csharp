# Finbourne.Sdk.Insights.Model.AuditDataSummary

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Count** | **int** | Optional | *No description available.* *(read-only)* |
| **Categories** | **Dictionary&lt;string, int&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new AuditDataSummary(
    count: 0,  // optional
    categories:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AuditDataSummary>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

