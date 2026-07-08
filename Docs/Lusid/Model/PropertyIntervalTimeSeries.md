# Finbourne.Sdk.Lusid.Model.PropertyIntervalTimeSeries

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The property key that this time series belongs to. |
| **Values** | [List&lt;PropertyInterval&gt;](PropertyInterval.md) | Required | The complete time series (history) of intervals for the property key. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PropertyIntervalTimeSeries(
    key: "...",  // required — The property key that this time series belongs to.
    values: new List<PropertyInterval>()  // required — The complete time series (history) of intervals for the property key.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PropertyIntervalTimeSeries>(json);
```

- [PropertyInterval](PropertyInterval.md) — used in `Values`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

