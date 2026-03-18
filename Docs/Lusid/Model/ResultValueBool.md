# Finbourne.Sdk.Lusid.Model.ResultValueBool

A simple result for a boolean value
> **Inherits from:** [ResultValue](ResultValue.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **bool** | Optional | The value itself |
| **ResultValueType** | **string** | Required | The available values are: ResultValue, ResultValueDictionary, ResultValue0D, ResultValueDecimal, ResultValueInt, ResultValueString, ResultValueBool, ResultValueCurrency, CashFlowValue, CashFlowValueSet, ResultValueLifeCycleEventValue, ResultValueDateTimeOffset Default: `ResultValueTypeEnum.ResultValueBool` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResultValueBool(
    value: true,  // optional — The value itself
    resultValueType: "..."  // required — The available values are: ResultValue, ResultValueDictionary, ResultValue0D, ResultValueDecimal, ResultValueInt, ResultValueString, ResultValueBool, ResultValueCurrency, CashFlowValue, CashFlowValueSet, ResultValueLifeCycleEventValue, ResultValueDateTimeOffset
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResultValueBool>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

