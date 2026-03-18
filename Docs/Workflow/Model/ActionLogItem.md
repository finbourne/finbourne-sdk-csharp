# Finbourne.Sdk.Workflow.Model.ActionLogItem

A log item for a given Action Log
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Timestamp** | **DateTimeOffset** | Required | The timestamp of the log item |
| **LogType** | **string** | Required | The type of log item |
| **Details** | **string** | Optional | The details of the log item |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ActionLogItem(
    timestamp: DateTimeOffset.Now,  // required — The timestamp of the log item
    logType: "...",  // required — The type of log item
    details: "..."  // optional — The details of the log item
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ActionLogItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

