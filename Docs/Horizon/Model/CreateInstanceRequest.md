# Finbourne.Sdk.Horizon.Model.CreateInstanceRequest

A request to add a new instance to an integration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstanceOptionalProps** | [Dictionary&lt;string, LusidPropertyDefinitionOverridesByType&gt;](LusidPropertyDefinitionOverridesByType.md) | Optional | *No description available.* |
| **IntegrationType** | **string** | Required | *No description available.* |
| **Name** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **Enabled** | **bool** | Required | *No description available.* |
| **Triggers** | [List&lt;Trigger&gt;](Trigger.md) | Required | *No description available.* |
| **Details** | **Object** | Required | Base DTO type of an integration configuration specific to the integration type.              N.B. ASP.NET Core model validation is normally applied automatically when [ApiController] is added to a controller, however it doesn&#39;t work here with the polymorphic integration subtypes of this class (see https://github.com/dotnet/aspnetcore/issues/27882). The workaround here is to implement the IValidatableObject interface and each subtype must call Validate() or ValidateContents() on its properties (the validation is not recursive).  Located in Horizon.Integrations.Web so both specific integration projects and Horizon.WebApi can reference it. |
| **PostProcessTasks** | [List&lt;PostProcessTask&gt;](PostProcessTask.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new CreateInstanceRequest(
    instanceOptionalProps: new LusidPropertyDefinitionOverridesByType(...),  // optional
    integrationType: "...",  // required
    name: "...",  // required
    description: "...",  // required
    enabled: true,  // required
    triggers: new List<Trigger>(),  // required
    details: ,  // required — Base DTO type of an integration configuration specific to the integration type.              N.B. ASP.NET Core model validation is normally applied automatically when [ApiController] is added to a controller, however it doesn&#39;t work here with the polymorphic integration subtypes of this class (see https://github.com/dotnet/aspnetcore/issues/27882). The workaround here is to implement the IValidatableObject interface and each subtype must call Validate() or ValidateContents() on its properties (the validation is not recursive).  Located in Horizon.Integrations.Web so both specific integration projects and Horizon.WebApi can reference it.
    postProcessTasks: new List<PostProcessTask>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateInstanceRequest>(json);
```


## Related Models

- [LusidPropertyDefinitionOverridesByType](LusidPropertyDefinitionOverridesByType.md)
- [Trigger](Trigger.md)
- [PostProcessTask](PostProcessTask.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

