# Finbourne.Sdk.Lusid.Model.DataTypeSummary

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TypeValueRange** | **string** | Required | Indicates the range of data acceptable by a data type. The available values are: Open, Closed |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | The display name of the data type. |
| **Description** | **string** | Required | The description of the data type. |
| **ValueType** | **string** | Required | The expected type of the values. The available values are: String, Int, Decimal, DateTime, Boolean, Map, List, PropertyArray, Percentage, Code, Id, Uri, CurrencyAndAmount, TradePrice, Currency, MetricValue, ResourceId, ResultValue, CutLocalTime, DateOrCutLabel, UnindexedText |
| **AcceptableValues** | **List&lt;string&gt;** | Optional | The acceptable set of values for this data type. Only applies to &#39;open&#39; value type range. |
| **UnitSchema** | **string** | Optional | The schema of the data type&#39;s units. The available values are: NoUnits, Basic, Iso4217Currency |
| **AcceptableUnits** | [List&lt;IUnitDefinitionDto&gt;](IUnitDefinitionDto.md) | Optional | The definitions of the acceptable units. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DataTypeSummary(
    typeValueRange: "...",  // required — Indicates the range of data acceptable by a data type. The available values are: Open, Closed
    id: new ResourceId(...),  // required
    displayName: "...",  // required — The display name of the data type.
    description: "...",  // required — The description of the data type.
    valueType: "...",  // required — The expected type of the values. The available values are: String, Int, Decimal, DateTime, Boolean, Map, List, PropertyArray, Percentage, Code, Id, Uri, CurrencyAndAmount, TradePrice, Currency, MetricValue, ResourceId, ResultValue, CutLocalTime, DateOrCutLabel, UnindexedText
    acceptableValues: ,  // optional — The acceptable set of values for this data type. Only applies to &#39;open&#39; value type range.
    unitSchema: "...",  // optional — The schema of the data type&#39;s units. The available values are: NoUnits, Basic, Iso4217Currency
    acceptableUnits: new List<IUnitDefinitionDto>(),  // optional — The definitions of the acceptable units.
    varVersion: new ModelVersion(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DataTypeSummary>(json);
```

- [ResourceId](ResourceId.md)
- [IUnitDefinitionDto](IUnitDefinitionDto.md) — used in `AcceptableUnits`
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

