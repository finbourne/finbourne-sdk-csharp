# Finbourne.Sdk.Scheduler.Model.TimeTrigger

Time-based trigger
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Expression** | **string** | Optional | Cron expression |
| **VarTimeZone** | **string** | Optional | Time zone of the Cron expression. If not provided, defaults to UTC |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new TimeTrigger(
    expression: "...",  // optional — Cron expression
    varTimeZone: "..."  // optional — Time zone of the Cron expression. If not provided, defaults to UTC
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TimeTrigger>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

