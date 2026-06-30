# Finbourne.Sdk.Workflow.Model.PerpetualProperty

A perpetual property (i.e. without effective dates) on a Workflow. A property is deleted by supplying a null Finbourne.Workflow.WebApi.Common.Dto.Json.Properties.PerpetualProperty.Value.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The property key in the form {domain}/{scope}/{code}. The domain must be &#39;Workflow&#39;. |
| **Value** | [PropertyValue](PropertyValue.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new PerpetualProperty(
    key: "...",  // required — The property key in the form {domain}/{scope}/{code}. The domain must be &#39;Workflow&#39;.
    value: new PropertyValue(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PerpetualProperty>(json);
```

- [PropertyValue](PropertyValue.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

