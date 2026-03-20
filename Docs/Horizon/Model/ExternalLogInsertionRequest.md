# Finbourne.Sdk.Horizon.Model.ExternalLogInsertionRequest

A request to insert external log records.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Logs** | [List&lt;ExternalLogRecord&gt;](ExternalLogRecord.md) | Required | The collection of external log records to insert. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ExternalLogInsertionRequest(
    logs: new List<ExternalLogRecord>()  // required — The collection of external log records to insert.
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

- [ExternalLogRecord](ExternalLogRecord.md) — used in `Logs`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

