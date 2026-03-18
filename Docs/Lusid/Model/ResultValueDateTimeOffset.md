# Finbourne.Sdk.Lusid.Model.ResultValueDateTimeOffset

A simple result for a date time value
> **Inherits from:** [ResultValue](ResultValue.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **DateTimeOffset** | Optional | The value itself |
| **Dimension** | **int?** | Optional | The dimension of the result. Can be null if there is no sensible way of defining the dimension. This field should not be  populate by the user on upsertion. |
| **ResultValueType** | **string** | Required | The available values are: ResultValue, ResultValueDictionary, ResultValue0D, ResultValueDecimal, ResultValueInt, ResultValueString, ResultValueBool, ResultValueCurrency, CashFlowValue, CashFlowValueSet, ResultValueLifeCycleEventValue, ResultValueDateTimeOffset Default: `ResultValueTypeEnum.ResultValueDateTimeOffset` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResultValueDateTimeOffset(
    value: DateTimeOffset.Now,  // optional — The value itself
    dimension: 0,  // optional — The dimension of the result. Can be null if there is no sensible way of defining the dimension. This field should not be  populate by the user on upsertion.
    resultValueType: "..."  // required — The available values are: ResultValue, ResultValueDictionary, ResultValue0D, ResultValueDecimal, ResultValueInt, ResultValueString, ResultValueBool, ResultValueCurrency, CashFlowValue, CashFlowValueSet, ResultValueLifeCycleEventValue, ResultValueDateTimeOffset
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResultValueDateTimeOffset>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

