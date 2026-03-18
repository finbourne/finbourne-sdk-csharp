# Finbourne.Sdk.Lusid.Model.LifeCycleEventValue

The instrument life cycle event result value type
> **Inherits from:** [ResultValue](ResultValue.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ResultValueType** | **string** | Required | The available values are: ResultValue, ResultValueDictionary, ResultValue0D, ResultValueDecimal, ResultValueInt, ResultValueString, ResultValueBool, ResultValueCurrency, CashFlowValue, CashFlowValueSet, ResultValueLifeCycleEventValue, ResultValueDateTimeOffset *(inherited)* |
| **EffectiveDate** | **DateTimeOffset** | Optional | The effective date of the event |
| **EventValues** | [ResultValueDictionary](ResultValueDictionary.md) | Optional | *No description available.* |
| **EventLineage** | [LifeCycleEventLineage](LifeCycleEventLineage.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LifeCycleEventValue(
    effectiveDate: DateTimeOffset.Now,  // optional — The effective date of the event
    eventValues: new ResultValueDictionary(...),  // optional
    eventLineage: new LifeCycleEventLineage(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LifeCycleEventValue>(json);
```


- [ResultValueDictionary](ResultValueDictionary.md)
- [LifeCycleEventLineage](LifeCycleEventLineage.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

