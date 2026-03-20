# Finbourne.Sdk.Horizon.Model.IntegrationInstanceResponse

Response representing an integration instance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | The unique identifier of the integration instance. |
| **IntegrationType** | **string** | Required | The type of the integration. |
| **Name** | **string** | Required | The name of the integration instance. |
| **Description** | **string** | Required | The description of the integration instance. |
| **Enabled** | **bool** | Required | Whether the integration instance is enabled. |
| **Triggers** | [List&lt;Trigger&gt;](Trigger.md) | Required | The triggers associated with the integration instance. |
| **Details** | **Object** | Required | Base DTO type of an integration configuration specific to the integration type.              N.B. ASP.NET Core model validation is normally applied automatically when [ApiController] is added to a controller, however it doesn&#39;t work here with the polymorphic integration subtypes of this class (see https://github.com/dotnet/aspnetcore/issues/27882). The workaround here is to implement the IValidatableObject interface and each subtype must call Validate() or ValidateContents() on its properties (the validation is not recursive).  Located in Horizon.Integrations.Web so both specific integration projects and Horizon.WebApi can reference it. |
| **PostProcessTasks** | [List&lt;PostProcessTask&gt;](PostProcessTask.md) | Required | The post process tasks associated with the integration instance. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationInstanceResponse(
    id: "...",  // required — The unique identifier of the integration instance.
    integrationType: "...",  // required — The type of the integration.
    name: "...",  // required — The name of the integration instance.
    description: "...",  // required — The description of the integration instance.
    enabled: true,  // required — Whether the integration instance is enabled.
    triggers: new List<Trigger>(),  // required — The triggers associated with the integration instance.
    details: ,  // required — Base DTO type of an integration configuration specific to the integration type.              N.B. ASP.NET Core model validation is normally applied automatically when [ApiController] is added to a controller, however it doesn&#39;t work here with the polymorphic integration subtypes of this class (see https://github.com/dotnet/aspnetcore/issues/27882). The workaround here is to implement the IValidatableObject interface and each subtype must call Validate() or ValidateContents() on its properties (the validation is not recursive).  Located in Horizon.Integrations.Web so both specific integration projects and Horizon.WebApi can reference it.
    postProcessTasks: new List<PostProcessTask>()  // required — The post process tasks associated with the integration instance.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationInstanceResponse>(json);
```

- [Trigger](Trigger.md) — used in `Triggers`
- [PostProcessTask](PostProcessTask.md) — used in `PostProcessTasks`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

