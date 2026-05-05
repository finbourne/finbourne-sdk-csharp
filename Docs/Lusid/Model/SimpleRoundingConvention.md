# Finbourne.Sdk.Lusid.Model.SimpleRoundingConvention

Certain bonds will follow certain rounding conventions.  For example, Thai government bonds will round accrued interest and cashflow values 2dp, whereas for  French government bonds, the rounding is to 7dp.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Precision** | **int** | Optional | The precision of the rounding. The decimal places or significant figures to which the rounding takes place.  Defaults to 0 if not set. |
| **RoundingType** | **string** | Optional | The type of rounding.  Default value: None. Available values: None, Down, Up, Nearest. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SimpleRoundingConvention(
    precision: 0,  // optional — The precision of the rounding. The decimal places or significant figures to which the rounding takes place.  Defaults to 0 if not set.
    roundingType: "..."  // optional — The type of rounding.  Default value: None. Available values: None, Down, Up, Nearest.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SimpleRoundingConvention>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

