# Finbourne.Sdk.Scheduler.Model.Trigger

Holds different kinds of triggers A schedule may only have one type of trigger
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TimeTrigger** | [TimeTrigger](TimeTrigger.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new Trigger(
    timeTrigger: new TimeTrigger(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Trigger>(json);
```


## Related Models

- [TimeTrigger](TimeTrigger.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

