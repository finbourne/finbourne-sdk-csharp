# Finbourne.Sdk.Lusid.Model.UpdateCutLabelDefinitionRequest

This request specifies a new Cut Label Definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **CutLocalTime** | [CutLocalTime](CutLocalTime.md) | Required | *No description available.* |
| **VarTimeZone** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateCutLabelDefinitionRequest(
    displayName: "...",  // required
    description: "...",  // optional
    cutLocalTime: new CutLocalTime(...),  // required
    varTimeZone: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateCutLabelDefinitionRequest>(json);
```

- [CutLocalTime](CutLocalTime.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

