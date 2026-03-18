# Finbourne.Sdk.Lusid.Model.YearMonthDay

A date in component form.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Year** | **int** | Required | The year of the date. |
| **Month** | **int** | Required | The month of the date. |
| **Day** | **int** | Required | The day in month of the date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new YearMonthDay(
    year: 0,  // required — The year of the date.
    month: 0,  // required — The month of the date.
    day: 0  // required — The day in month of the date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<YearMonthDay>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

