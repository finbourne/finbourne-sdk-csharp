# Finbourne.Sdk.Lusid.Model.ScenarioReference

A reference to a stored Scenario, identified by scope and code, optionally pinned to an AsAt version.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope of the scenario to apply. |
| **Code** | **string** | Required | The code of the scenario to apply. |
| **AsAt** | **DateTimeOffset?** | Optional | The AsAt of the scenario version to apply. If not supplied, the latest version is used. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ScenarioReference(
    scope: "...",  // required — The scope of the scenario to apply.
    code: "...",  // required — The code of the scenario to apply.
    asAt: DateTimeOffset.Now  // optional — The AsAt of the scenario version to apply. If not supplied, the latest version is used.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScenarioReference>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

