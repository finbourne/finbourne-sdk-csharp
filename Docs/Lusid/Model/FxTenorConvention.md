# Finbourne.Sdk.Lusid.Model.FxTenorConvention

A wrapper of conventions that should be used when interpreting tenors in the context of FX.  For instance, can be used to control how tenors are interpreted on an FxForwardTenorCurveData instance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CalendarCode** | **string** | Required | The code of the holiday calendar that should be used when interpreting FX tenors. |
| **SpotDays** | **int** | Required | The minimum number of business days that must pass within this calendar when calculating the spot date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxTenorConvention(
    calendarCode: "...",  // required — The code of the holiday calendar that should be used when interpreting FX tenors.
    spotDays: 0  // required — The minimum number of business days that must pass within this calendar when calculating the spot date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FxTenorConvention>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

