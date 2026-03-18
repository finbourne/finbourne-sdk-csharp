# Finbourne.Sdk.Lusid.Model.PerpetualProperty

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key of the property. This takes the format {domain}/{scope}/{code} e.g. &#39;Instrument/system/Name&#39; or &#39;Transaction/strategy/quantsignal&#39;. |
| **Value** | [PropertyValue](PropertyValue.md) | Optional | *No description available.* |
| **ReferenceData** | [Dictionary&lt;string, PropertyReferenceDataValue&gt;](PropertyReferenceDataValue.md) | Optional | The ReferenceData linked to the value of the property. The ReferenceData is taken from the DataType on the PropertyDefinition that defines the property. *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PerpetualProperty(
    key: "...",  // required — The key of the property. This takes the format {domain}/{scope}/{code} e.g. &#39;Instrument/system/Name&#39; or &#39;Transaction/strategy/quantsignal&#39;.
    value: new PropertyValue(...),  // optional
    referenceData: new PropertyReferenceDataValue(...)  // optional — The ReferenceData linked to the value of the property. The ReferenceData is taken from the DataType on the PropertyDefinition that defines the property.
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
- [PropertyReferenceDataValue](PropertyReferenceDataValue.md) — used in `ReferenceData`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

