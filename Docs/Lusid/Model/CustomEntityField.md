# Finbourne.Sdk.Lusid.Model.CustomEntityField

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of the field in the custom entity type definition. |
| **Value** | **Object** | Optional | The value for the field. |
| **EffectiveFrom** | **DateTimeOffset?** | Optional | The effective datetime from which the field&#39;s value is valid. For timeVariant fields, this defaults to the beginning of time. |
| **EffectiveUntil** | **DateTimeOffset?** | Optional | The effective datetime until which the field&#39;s value is valid. If not supplied, the value will be valid indefinitely or until the next “effectiveFrom” date of the field. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomEntityField(
    name: "...",  // required — The name of the field in the custom entity type definition.
    value: ,  // optional — The value for the field.
    effectiveFrom: DateTimeOffset.Now,  // optional — The effective datetime from which the field&#39;s value is valid. For timeVariant fields, this defaults to the beginning of time.
    effectiveUntil: DateTimeOffset.Now  // optional — The effective datetime until which the field&#39;s value is valid. If not supplied, the value will be valid indefinitely or until the next “effectiveFrom” date of the field.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomEntityField>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

