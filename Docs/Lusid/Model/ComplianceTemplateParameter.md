# Finbourne.Sdk.Lusid.Model.ComplianceTemplateParameter

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name for the required Compliance Template Parameter |
| **Description** | **string** | Required | The description for the required Compliance Template Parameter |
| **Type** | **string** | Required | The type for the required Compliance Template Parameter |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceTemplateParameter(
    name: "...",  // required — The name for the required Compliance Template Parameter
    description: "...",  // required — The description for the required Compliance Template Parameter
    type: "..."  // required — The type for the required Compliance Template Parameter
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceTemplateParameter>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

