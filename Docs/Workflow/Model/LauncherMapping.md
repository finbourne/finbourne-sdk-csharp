# Finbourne.Sdk.Workflow.Model.LauncherMapping

A value a Launcher either gives as it is or takes from somewhere.              Exactly one of Finbourne.Workflow.WebApi.Common.Dto.Json.Launchers.LauncherMapping.SetTo or Finbourne.Workflow.WebApi.Common.Dto.Json.Launchers.LauncherMapping.MapFrom must be given. Only an Event Launcher has an event to take a value from, so a Schedule Launcher can only use Finbourne.Workflow.WebApi.Common.Dto.Json.Launchers.LauncherMapping.SetTo
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SetTo** | **string** | Optional | The value to use, given as it is |
| **MapFrom** | **string** | Optional | The path the value is taken from, for example header.userId |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LauncherMapping(
    setTo: "...",  // optional — The value to use, given as it is
    mapFrom: "..."  // optional — The path the value is taken from, for example header.userId
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LauncherMapping>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

