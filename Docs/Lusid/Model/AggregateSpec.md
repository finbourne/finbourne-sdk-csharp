# Finbourne.Sdk.Lusid.Model.AggregateSpec

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key that uniquely identifies a queryable address in Lusid. |
| **Op** | **string** | Required | The available values are: Sum, DefaultSum, Proportion, Average, Count, Min, Max, Value, SumOfPositiveValues, SumOfNegativeValues, SumOfAbsoluteValues, ProportionOfAbsoluteValues, SumCumulativeInAdvance, SumCumulativeInArrears |
| **Options** | **Dictionary&lt;string, Object&gt;** | Optional | Additional options to apply when performing computations. Options that do not apply to the Key will be  ignored. Option values can be boolean, numeric, string or date-time. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregateSpec(
    key: "...",  // required — The key that uniquely identifies a queryable address in Lusid.
    op: "...",  // required — The available values are: Sum, DefaultSum, Proportion, Average, Count, Min, Max, Value, SumOfPositiveValues, SumOfNegativeValues, SumOfAbsoluteValues, ProportionOfAbsoluteValues, SumCumulativeInAdvance, SumCumulativeInArrears
    options:   // optional — Additional options to apply when performing computations. Options that do not apply to the Key will be  ignored. Option values can be boolean, numeric, string or date-time.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregateSpec>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

