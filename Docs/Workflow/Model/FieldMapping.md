# Finbourne.Sdk.Workflow.Model.FieldMapping

Defines a single Field map
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MapFrom** | **string** | Optional | The field to map from |
| **SetTo** | **Object** | Optional | The (constant) value to set |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new FieldMapping(
    mapFrom: "...",  // optional — The field to map from
    setTo:   // optional — The (constant) value to set
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FieldMapping>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

