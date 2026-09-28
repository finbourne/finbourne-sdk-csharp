# Finbourne.Sdk.Workflow.Model.CreateLauncherRequest

Contains information for creating a Launcher on a Workflow.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LauncherId** | **string** | Required | The identifier of the Launcher inside its Workflow |
| **DisplayName** | **string** | Required | Human-readable name |
| **Description** | **string** | Optional | Human-readable description |
| **Status** | **string** | Required | The current status of the Launcher. One of - Active, Inactive |
| **LauncherDetails** | [LauncherDetails](LauncherDetails.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CreateLauncherRequest(
    launcherId: "...",  // required — The identifier of the Launcher inside its Workflow
    displayName: "...",  // required — Human-readable name
    description: "...",  // optional — Human-readable description
    status: "...",  // required — The current status of the Launcher. One of - Active, Inactive
    launcherDetails: new LauncherDetails(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateLauncherRequest>(json);
```

- [LauncherDetails](LauncherDetails.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

