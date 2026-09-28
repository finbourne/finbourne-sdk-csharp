# Finbourne.Sdk.Workflow.Model.LauncherDetails

What makes a Launcher start a run of its Workflow, and what it puts on the root task when it does.              The members here belong to every Launcher. Finbourne.Workflow.WebApi.Common.Dto.Json.Launchers.Requests.ScheduleLauncherDetails and Finbourne.Workflow.WebApi.Common.Dto.Json.Launchers.Requests.EventLauncherDetails add what only a schedule or only an event needs

## oneOf Type

`LauncherDetails` can be one of the following types:

* [EventLauncherDetails](./EventLauncherDetails.md)
* [ScheduleLauncherDetails](./ScheduleLauncherDetails.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var inner = new EventLauncherDetails(...);
var instance = new LauncherDetails(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LauncherDetails>(json);
```

## Related Models

- [EventLauncherDetails](./EventLauncherDetails.md)
- [ScheduleLauncherDetails](./ScheduleLauncherDetails.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

