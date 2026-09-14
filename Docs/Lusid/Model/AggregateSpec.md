# Finbourne.Sdk.Lusid.Model.AggregateSpec

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key that uniquely identifies a queryable address in Lusid. |
| **Op** | **string** | Required | Available values: Sum, DefaultSum, Proportion, Average, Count, Min, Max, Value, SumOfPositiveValues, SumOfNegativeValues, SumOfAbsoluteValues, ProportionOfAbsoluteValues, SumCumulativeInAdvance, SumCumulativeInArrears. |
| **Options** | **Dictionary&lt;string, Object&gt;** | Optional | Additional options to apply when performing computations. Options that do not apply to the Key will be  ignored. Option values can be boolean, numeric, string or date-time. |
| **ReturnAs** | **string** | Optional | Optional client-chosen name for this metric. When supplied, the corresponding column in the returned  data is keyed by this name instead of the serialised address key (with options), letting callers  associate each requested metric with its result without reconstructing the key serialisation.  Names must be unique within a request, start with a letter and contain only letters, digits,  underscores or hyphens. When omitted, the column is keyed by the serialised address key as before. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregateSpec(
    key: "...",  // required — The key that uniquely identifies a queryable address in Lusid.
    op: "...",  // required — Available values: Sum, DefaultSum, Proportion, Average, Count, Min, Max, Value, SumOfPositiveValues, SumOfNegativeValues, SumOfAbsoluteValues, ProportionOfAbsoluteValues, SumCumulativeInAdvance, SumCumulativeInArrears.
    options: ,  // optional — Additional options to apply when performing computations. Options that do not apply to the Key will be  ignored. Option values can be boolean, numeric, string or date-time.
    returnAs: "..."  // optional — Optional client-chosen name for this metric. When supplied, the corresponding column in the returned  data is keyed by this name instead of the serialised address key (with options), letting callers  associate each requested metric with its result without reconstructing the key serialisation.  Names must be unique within a request, start with a letter and contain only letters, digits,  underscores or hyphens. When omitted, the column is keyed by the serialised address key as before.
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

