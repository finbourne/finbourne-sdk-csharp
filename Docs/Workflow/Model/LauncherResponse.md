# Finbourne.Sdk.Workflow.Model.LauncherResponse

A Launcher, which starts a run of one Workflow either at the times a schedule gives or when a matching event arrives
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WorkflowId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **LauncherId** | **string** | Required | The identifier of this Launcher inside its Workflow |
| **DisplayName** | **string** | Required | Human-readable name |
| **Description** | **string** | Optional | Human-readable description |
| **Status** | **string** | Required | The current status of the Launcher. One of - Active, Inactive |
| **LauncherDetails** | [LauncherDetailsResponse](LauncherDetailsResponse.md) | Required | *No description available.* |
| **Summaries** | [LauncherSummaries](LauncherSummaries.md) | Optional | *No description available.* |
| **VarVersion** | [VersionInfo](VersionInfo.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LauncherResponse(
    workflowId: new ResourceId(...),  // required
    launcherId: "...",  // required — The identifier of this Launcher inside its Workflow
    displayName: "...",  // required — Human-readable name
    description: "...",  // optional — Human-readable description
    status: "...",  // required — The current status of the Launcher. One of - Active, Inactive
    launcherDetails: new LauncherDetailsResponse(...),  // required
    summaries: new LauncherSummaries(...),  // optional
    varVersion: new VersionInfo(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LauncherResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [LauncherDetailsResponse](LauncherDetailsResponse.md)
- [LauncherSummaries](LauncherSummaries.md)
- [VersionInfo](VersionInfo.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

