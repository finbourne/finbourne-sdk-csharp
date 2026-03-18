# Finbourne.Sdk.Lusid.Model.PropertyInterval

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | [PropertyValue](PropertyValue.md) | Required | *No description available.* |
| **EffectiveRange** | [DateRange](DateRange.md) | Required | *No description available.* |
| **AsAtRange** | [DateRange](DateRange.md) | Required | *No description available.* |
| **Status** | **string** | Required | Indicates whether the value is part of the prevailing effective date timeline for the requested asAt date, or whether it has been superseded by correctional activity |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PropertyInterval(
    value: new PropertyValue(...),  // required
    effectiveRange: new DateRange(...),  // required
    asAtRange: new DateRange(...),  // required
    status: "..."  // required — Indicates whether the value is part of the prevailing effective date timeline for the requested asAt date, or whether it has been superseded by correctional activity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PropertyInterval>(json);
```


## Related Models

- [PropertyValue](PropertyValue.md)
- [DateRange](DateRange.md)
- [DateRange](DateRange.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

