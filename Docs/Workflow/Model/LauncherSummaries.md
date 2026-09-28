# Finbourne.Sdk.Workflow.Model.LauncherSummaries

Sentences that say what a Launcher does, meant to be shown to a person.              These are rendered on read from the stored Launcher details. They are never stored and never accepted on a write, so the same Launcher always reads back the same summaries
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Schedule** | **string** | Optional | A sentence that says when the Launcher starts a run, for example \&quot;At 09:00 every weekday, London time\&quot;.              Null for an Event Launcher, which has no schedule |
| **Fields** | **Dictionary&lt;string, string&gt;** | Optional | A sentence for each field of the root task the Launcher fills, keyed by the field name on the root task definition. Empty when the Launcher fills no fields |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LauncherSummaries(
    schedule: "...",  // optional — A sentence that says when the Launcher starts a run, for example \&quot;At 09:00 every weekday, London time\&quot;.              Null for an Event Launcher, which has no schedule
    fields:   // optional — A sentence for each field of the root task the Launcher fills, keyed by the field name on the root task definition. Empty when the Launcher fills no fields
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LauncherSummaries>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

