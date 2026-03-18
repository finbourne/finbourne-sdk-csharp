# Finbourne.Sdk.Lusid.Model.ResultValue0D

Result value representing a 0D result. These results can be equipped with a unit
> **Inherits from:** [ResultValue](ResultValue.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Units** | **string** | Optional | Unit of the result |
| **Value** | **decimal** | Optional | The value of the result |
| **Dimension** | **int?** | Optional | The dimension of the result. Can be null if there is no sensible way of defining the dimension. This field should not be  populate by the user on upsertion. |
| **ResultValueType** | **string** | Required | The available values are: ResultValue, ResultValueDictionary, ResultValue0D, ResultValueDecimal, ResultValueInt, ResultValueString, ResultValueBool, ResultValueCurrency, CashFlowValue, CashFlowValueSet, ResultValueLifeCycleEventValue, ResultValueDateTimeOffset Default: `ResultValueTypeEnum.ResultValue0D` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResultValue0D(
    units: "...",  // optional — Unit of the result
    value: 0.0d,  // optional — The value of the result
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
var instance = JsonConvert.DeserializeObject<ResultValue0D>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

