# Finbourne.Sdk.Horizon.Model.ExternalLogInsertionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Logs** | [List&lt;ExternalLogRecord&gt;](ExternalLogRecord.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ExternalLogInsertionRequest(
    logs: new List<ExternalLogRecord>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExternalLogInsertionRequest>(json);
```


## Related Models

- [ExternalLogRecord](ExternalLogRecord.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

