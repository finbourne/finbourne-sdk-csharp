# Finbourne.Sdk.Horizon.Model.IntegrationInstance

Response containing an integration instance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | Identifies the instance within the integration. |
| **IntegrationType** | **string** | Required | The integration type. |
| **Name** | **string** | Required | Name of the instance. |
| **Description** | **string** | Required | Description of the instance. |
| **Enabled** | **bool** | Required | If true the instance will be executed if its trigger is satisfied. |
| **Triggers** | [List&lt;Trigger&gt;](Trigger.md) | Required | Defines what triggers execution of the instance. |
| **Details** | **Object** | Required | Base DTO type of an integration configuration specific to the integration type.              N.B. ASP.NET Core model validation is normally applied automatically when [ApiController] is added to a controller, however it doesn&#39;t work here with the polymorphic integration subtypes of this class (see https://github.com/dotnet/aspnetcore/issues/27882). The workaround here is to implement the IValidatableObject interface and each subtype must call Validate() or ValidateContents() on its properties (the validation is not recursive).  Located in Horizon.Integrations.Web so both specific integration projects and Horizon.WebApi can reference it. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationInstance(
    id: "...",  // required — Identifies the instance within the integration.
    integrationType: "...",  // required — The integration type.
    name: "...",  // required — Name of the instance.
    description: "...",  // required — Description of the instance.
    enabled: true,  // required — If true the instance will be executed if its trigger is satisfied.
    triggers: new List<Trigger>(),  // required — Defines what triggers execution of the instance.
    details:   // required — Base DTO type of an integration configuration specific to the integration type.              N.B. ASP.NET Core model validation is normally applied automatically when [ApiController] is added to a controller, however it doesn&#39;t work here with the polymorphic integration subtypes of this class (see https://github.com/dotnet/aspnetcore/issues/27882). The workaround here is to implement the IValidatableObject interface and each subtype must call Validate() or ValidateContents() on its properties (the validation is not recursive).  Located in Horizon.Integrations.Web so both specific integration projects and Horizon.WebApi can reference it.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationInstance>(json);
```

- [Trigger](Trigger.md) — used in `Triggers`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

