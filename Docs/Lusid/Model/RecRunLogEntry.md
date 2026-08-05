# Finbourne.Sdk.Lusid.Model.RecRunLogEntry

A single run within an instance's run log. All runs share the same effective dates (frozen at  instantiation); each has a different asAt, advanced on re-run.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunNumber** | **int** | Required | The run number within the instance. Increments with each re-run. |
| **RunAsAt** | **DateTimeOffset** | Required | The asAt datetime at which the run happened. |
| **SupersededAsAt** | **DateTimeOffset?** | Optional | The asAt datetime at which this run was superseded by a subsequent run. |
| **DatesReconciled** | [RecDatesReconciled](RecDatesReconciled.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecRunLogEntry(
    runNumber: 0,  // required — The run number within the instance. Increments with each re-run.
    runAsAt: DateTimeOffset.Now,  // required — The asAt datetime at which the run happened.
    supersededAsAt: DateTimeOffset.Now,  // optional — The asAt datetime at which this run was superseded by a subsequent run.
    datesReconciled: new RecDatesReconciled(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecRunLogEntry>(json);
```

- [RecDatesReconciled](RecDatesReconciled.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

