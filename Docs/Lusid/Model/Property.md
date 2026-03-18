# Finbourne.Sdk.Lusid.Model.Property

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key of the property. This takes the format {domain}/{scope}/{code} e.g. &#39;Instrument/system/Name&#39; or &#39;Transaction/strategy/quantsignal&#39;. |
| **Value** | [PropertyValue](PropertyValue.md) | Optional | *No description available.* |
| **EffectiveFrom** | **DateTimeOffset?** | Optional | The effective datetime from which the property is valid. |
| **EffectiveUntil** | **DateTimeOffset?** | Optional | The effective datetime until which the property is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveFrom&#39; datetime of the property. |
| **ReferenceData** | [Dictionary&lt;string, PropertyReferenceDataValue&gt;](PropertyReferenceDataValue.md) | Optional | The ReferenceData linked to the value of the property. The ReferenceData is taken from the DataType on the PropertyDefinition that defines the property. *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Property(
    key: "...",  // required — The key of the property. This takes the format {domain}/{scope}/{code} e.g. &#39;Instrument/system/Name&#39; or &#39;Transaction/strategy/quantsignal&#39;.
    value: new PropertyValue(...),  // optional
    effectiveFrom: DateTimeOffset.Now,  // optional — The effective datetime from which the property is valid.
    effectiveUntil: DateTimeOffset.Now,  // optional — The effective datetime until which the property is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveFrom&#39; datetime of the property.
    referenceData: new PropertyReferenceDataValue(...)  // optional — The ReferenceData linked to the value of the property. The ReferenceData is taken from the DataType on the PropertyDefinition that defines the property.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Property>(json);
```

- [PropertyValue](PropertyValue.md)
- [PropertyReferenceDataValue](PropertyReferenceDataValue.md) — used in `ReferenceData`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

