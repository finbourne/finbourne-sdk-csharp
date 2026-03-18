# Finbourne.Sdk.Lusid.Model.CreateDataTypeRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope that the data type will be created in. |
| **Code** | **string** | Required | The code of the data type. Together with the scope this uniquely defines the data type. |
| **TypeValueRange** | **string** | Required | Indicates the range of data acceptable by a data type. The available values are: Open, Closed |
| **DisplayName** | **string** | Required | The display name of the data type. |
| **Description** | **string** | Required | The description of the data type. |
| **ValueType** | **string** | Required | The expected type of the values. The available values are: String, Int, Decimal, DateTime, Boolean, Map, List, PropertyArray, Percentage, Code, Id, Uri, CurrencyAndAmount, TradePrice, Currency, MetricValue, ResourceId, ResultValue, CutLocalTime, DateOrCutLabel, UnindexedText |
| **AcceptableValues** | **List&lt;string&gt;** | Optional | The acceptable set of values for this data type. Only applies to &#39;open&#39; value type range. |
| **UnitSchema** | **string** | Optional | The schema of the data type&#39;s units. The available values are: NoUnits, Basic, Iso4217Currency |
| **AcceptableUnits** | [List&lt;CreateUnitDefinition&gt;](CreateUnitDefinition.md) | Optional | The definitions of the acceptable units. |
| **ReferenceData** | [ReferenceData](ReferenceData.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateDataTypeRequest(
    scope: "...",  // required — The scope that the data type will be created in.
    code: "...",  // required — The code of the data type. Together with the scope this uniquely defines the data type.
    typeValueRange: "...",  // required — Indicates the range of data acceptable by a data type. The available values are: Open, Closed
    displayName: "...",  // required — The display name of the data type.
    description: "...",  // required — The description of the data type.
    valueType: "...",  // required — The expected type of the values. The available values are: String, Int, Decimal, DateTime, Boolean, Map, List, PropertyArray, Percentage, Code, Id, Uri, CurrencyAndAmount, TradePrice, Currency, MetricValue, ResourceId, ResultValue, CutLocalTime, DateOrCutLabel, UnindexedText
    acceptableValues: ,  // optional — The acceptable set of values for this data type. Only applies to &#39;open&#39; value type range.
    unitSchema: "...",  // optional — The schema of the data type&#39;s units. The available values are: NoUnits, Basic, Iso4217Currency
    acceptableUnits: new List<CreateUnitDefinition>(),  // optional — The definitions of the acceptable units.
    referenceData: new ReferenceData(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateDataTypeRequest>(json);
```

- [CreateUnitDefinition](CreateUnitDefinition.md) — used in `AcceptableUnits`
- [ReferenceData](ReferenceData.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

