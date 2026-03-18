# Finbourne.Sdk.Workflow.Model.CutLabelReference

A reference to a Cut Label in LUSID. The time zone of the Cut Label will be used
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | Code of the Cut Label |
| **Type** | **string** | Required | The type of Time of Day |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CutLabelReference(
    code: "...",  // required — Code of the Cut Label
    type: "..."  // required — The type of Time of Day
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CutLabelReference>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

