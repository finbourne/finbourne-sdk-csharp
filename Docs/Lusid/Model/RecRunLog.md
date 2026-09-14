# Finbourne.Sdk.Lusid.Model.RecRunLog

One rec type's run history within a rec instance: its most recent runs, and the total number of runs those  were taken from.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunCount** | **int** | Required | The total number of runs of this rec type, which is not necessarily the number returned. A value greater than ten means runs has been truncated; the runs beyond it remain retrievable from previousRuns on the rec type&#39;s result set. |
| **Runs** | [List&lt;RecRunLogEntry&gt;](RecRunLogEntry.md) | Required | The ten most recent runs of this rec type, ordered by run number descending, so the current run is always the first entry. Exactly one entry has a null supersededAsAt. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecRunLog(
    runCount: 0,  // required — The total number of runs of this rec type, which is not necessarily the number returned. A value greater than ten means runs has been truncated; the runs beyond it remain retrievable from previousRuns on the rec type&#39;s result set.
    runs: new List<RecRunLogEntry>()  // required — The ten most recent runs of this rec type, ordered by run number descending, so the current run is always the first entry. Exactly one entry has a null supersededAsAt.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecRunLog>(json);
```

- [RecRunLogEntry](RecRunLogEntry.md) — used in `Runs`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

