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
| **Details** | **Object** | Required | *No description available.* |


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
    details:   // required
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

