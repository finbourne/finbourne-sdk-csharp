# Finbourne.Sdk.Lusid.Model.RelationalDataPointFieldValueResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **Object** | Required | The value of the field. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RelationalDataPointFieldValueResponse(
    value:   // required — The value of the field.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelationalDataPointFieldValueResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

