# Finbourne.Sdk.Workflow.Model.LauncherDetailsResponse

What makes a Launcher start a run of its Workflow, and what it puts on the root task when it does, in a read only form.              The members here belong to every Launcher. Finbourne.Workflow.WebApi.Common.Dto.Json.Launchers.ScheduleLauncherDetailsResponse and Finbourne.Workflow.WebApi.Common.Dto.Json.Launchers.EventLauncherDetailsResponse add what only a schedule or only an event needs

## oneOf Type

`LauncherDetailsResponse` can be one of the following types:

* [EventLauncherDetailsResponse](./EventLauncherDetailsResponse.md)
* [ScheduleLauncherDetailsResponse](./ScheduleLauncherDetailsResponse.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var inner = new EventLauncherDetailsResponse(...);
var instance = new LauncherDetailsResponse(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LauncherDetailsResponse>(json);
```

## Related Models

- [EventLauncherDetailsResponse](./EventLauncherDetailsResponse.md)
- [ScheduleLauncherDetailsResponse](./ScheduleLauncherDetailsResponse.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

