# Finbourne.Sdk.Lusid.Model.TemplateField

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FieldName** | **string** | Required | *No description available.* |
| **Specificity** | **string** | Required | Available values: AllEventsAndHoldings, InstrumentEventType, ElectionType. |
| **Description** | **string** | Required | *No description available.* |
| **Type** | **string** | Required | Available values: String, Decimal, InstrumentScope, Currency, DateTime, PriceType, InstrumentId, PropertyKey, Boolean. |
| **Availability** | **string** | Required | Available values: Guaranteed, DataDependent, Informational. |
| **Usage** | **List&lt;string&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TemplateField(
    fieldName: "...",  // required
    specificity: "...",  // required — Available values: AllEventsAndHoldings, InstrumentEventType, ElectionType.
    description: "...",  // required
    type: "...",  // required — Available values: String, Decimal, InstrumentScope, Currency, DateTime, PriceType, InstrumentId, PropertyKey, Boolean.
    availability: "...",  // required — Available values: Guaranteed, DataDependent, Informational.
    usage:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TemplateField>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

