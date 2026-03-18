# Finbourne.Sdk.Lusid.Model.CashFlowValue

Result class for a cash flow value
> **Inherits from:** [ResultValue](ResultValue.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentDate** | **DateTimeOffset** | Required | The payment date of the cash flow |
| **Diagnostics** | [ResultValueDictionary](ResultValueDictionary.md) | Optional | *No description available.* |
| **CashFlowLineage** | [CashFlowLineage](CashFlowLineage.md) | Optional | *No description available.* |
| **PaymentAmount** | **decimal** | Required | The amount paid or received |
| **PaymentCcy** | **string** | Required | The currency of the transaction |
| **ResultValueType** | **string** | Required | The available values are: ResultValue, ResultValueDictionary, ResultValue0D, ResultValueDecimal, ResultValueInt, ResultValueString, ResultValueBool, ResultValueCurrency, CashFlowValue, CashFlowValueSet, ResultValueLifeCycleEventValue, ResultValueDateTimeOffset Default: `ResultValueTypeEnum.CashFlowValue` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CashFlowValue(
    paymentDate: DateTimeOffset.Now,  // required — The payment date of the cash flow
    diagnostics: new ResultValueDictionary(...),  // optional
    cashFlowLineage: new CashFlowLineage(...),  // optional
    paymentAmount: 0.0d,  // required — The amount paid or received
    paymentCcy: "...",  // required — The currency of the transaction
    resultValueType: "..."  // required — The available values are: ResultValue, ResultValueDictionary, ResultValue0D, ResultValueDecimal, ResultValueInt, ResultValueString, ResultValueBool, ResultValueCurrency, CashFlowValue, CashFlowValueSet, ResultValueLifeCycleEventValue, ResultValueDateTimeOffset
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CashFlowValue>(json);
```


- [ResultValueDictionary](ResultValueDictionary.md)
- [CashFlowLineage](CashFlowLineage.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

