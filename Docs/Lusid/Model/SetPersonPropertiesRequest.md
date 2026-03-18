# Finbourne.Sdk.Lusid.Model.SetPersonPropertiesRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Required | Properties to set for a Person. All time-variant properties must have same EffectiveFrom date. Properties not included in the request will not be amended. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SetPersonPropertiesRequest(
    properties: new Property(...)  // required — Properties to set for a Person. All time-variant properties must have same EffectiveFrom date. Properties not included in the request will not be amended.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SetPersonPropertiesRequest>(json);
```


## Related Models

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

