# Finbourne.Sdk.Lusid.Model.QualifierDefinition

A qualifier as returned on read: the request shape plus the value type resolved from its data type.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Optional | The key by which the qualifier is addressed, for example &#39;direction&#39;. Addressed in filters, sort orders and derivation formulae as Properties[{propertyKey}].Qualifiers[{qualifierKey}]. Validated under the same rules as a property code. |
| **DisplayName** | **string** | Optional | The display name of the qualifier. |
| **Description** | **string** | Optional | Describes the qualifier. Optional; null where not supplied. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **ValueType** | **string** | Optional | The type of value this qualifier carries, resolved from its data type. Available values: String, Int, Decimal, DateTime, Boolean, Map, List, PropertyArray, Percentage, Code, Id, Uri, CurrencyAndAmount, TradePrice, Currency, MetricValue, ResourceId, ResultValue, CutLocalTime, DateOrCutLabel, UnindexedText. |
| **IsRequired** | **bool** | Optional | Whether a value for this qualifier must be supplied when a value of the property is written. Defaults to false, and is returned as a boolean rather than as null. Validated on write only, so setting it true does not retroactively invalidate values stored before the change. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QualifierDefinition(
    key: "...",  // optional — The key by which the qualifier is addressed, for example &#39;direction&#39;. Addressed in filters, sort orders and derivation formulae as Properties[{propertyKey}].Qualifiers[{qualifierKey}]. Validated under the same rules as a property code.
    displayName: "...",  // optional — The display name of the qualifier.
    description: "...",  // optional — Describes the qualifier. Optional; null where not supplied.
    dataTypeId: new ResourceId(...),  // optional
    valueType: "...",  // optional — The type of value this qualifier carries, resolved from its data type. Available values: String, Int, Decimal, DateTime, Boolean, Map, List, PropertyArray, Percentage, Code, Id, Uri, CurrencyAndAmount, TradePrice, Currency, MetricValue, ResourceId, ResultValue, CutLocalTime, DateOrCutLabel, UnindexedText.
    isRequired: true  // optional — Whether a value for this qualifier must be supplied when a value of the property is written. Defaults to false, and is returned as a boolean rather than as null. Validated on write only, so setting it true does not retroactively invalidate values stored before the change.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QualifierDefinition>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

