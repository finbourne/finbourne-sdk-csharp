# Finbourne.Sdk.Workflow.Model.LaunchedBy

The Launcher that started a run of a Workflow
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LauncherId** | **string** | Required | The ID of the Launcher inside its Workflow |
| **LauncherType** | **string** | Required | The type of Launcher. One of - Schedule, Event |
| **LauncherAsAt** | **DateTimeOffset** | Required | The version.asAtModified of the Launcher definition that fired |
| **FiredAt** | **DateTimeOffset** | Required | When the Launcher fired. For a Schedule Launcher this is the scheduled trigger time, and for an Event Launcher it is the timestamp of the event |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LaunchedBy(
    launcherId: "...",  // required — The ID of the Launcher inside its Workflow
    launcherType: "...",  // required — The type of Launcher. One of - Schedule, Event
    launcherAsAt: DateTimeOffset.Now,  // required — The version.asAtModified of the Launcher definition that fired
    firedAt: DateTimeOffset.Now  // required — When the Launcher fired. For a Schedule Launcher this is the scheduled trigger time, and for an Event Launcher it is the timestamp of the event
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LaunchedBy>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

