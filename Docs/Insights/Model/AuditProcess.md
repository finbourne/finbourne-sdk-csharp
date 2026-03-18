# Finbourne.Sdk.Insights.Model.AuditProcess

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | *No description available.* |
| **RunId** | **string** | Required | *No description available.* |
| **StartTime** | **DateTimeOffset** | Required | *No description available.* |
| **EndTime** | **DateTimeOffset?** | Optional | *No description available.* |
| **Succeeded** | **bool?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new AuditProcess(
    name: "...",  // required
    runId: "...",  // required
    startTime: DateTimeOffset.Now,  // required
    endTime: DateTimeOffset.Now,  // optional
    succeeded: true  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AuditProcess>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

