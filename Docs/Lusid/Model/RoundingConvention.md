# Finbourne.Sdk.Lusid.Model.RoundingConvention

Certain bonds will follow certain rounding conventions.  For example, Thai government bonds will round accrued interest and cashflow values 2dp, whereas for  French government bonds, the rounding is to 7dp.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FaceValue** | **decimal** | Optional | The face value to round against.  The number to be rounded is scaled to this face value before being rounded, and then re-scaled to the holding amount.  For example if rounding an accrued interest value using a FaceValue of 1,000, but 10,000 units are held,  then the initial calculated value would be divided by 10,000, then multiplied by 1,000 and rounded per the convention.  The result of this would then be divided by 1,000 and multiplied by 10,000 to get the final value. |
| **Precision** | **int** | Optional | The precision of the rounding.  The decimal places to which the rounding takes place.  Defaults to 0 if not set. |
| **RoundingTarget** | **string** | Optional | The target of the rounding convention.  Accepted values are &#39;AccruedInterest&#39;, &#39;Cashflows&#39;, or &#39;All&#39;    Supported string (enumeration) values are: [All, AccruedInterest, Cashflows].  Defaults to \&quot;All\&quot; if not set. |
| **RoundingType** | **string** | Optional | The type of rounding.  e.g. Round Up, Round Down    Supported string (enumeration) values are: [Down, Up, Floor, Ceiling, Nearest].  Defaults to \&quot;Nearest\&quot; if not set. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RoundingConvention(
    faceValue: 0.0d,  // optional — The face value to round against.  The number to be rounded is scaled to this face value before being rounded, and then re-scaled to the holding amount.  For example if rounding an accrued interest value using a FaceValue of 1,000, but 10,000 units are held,  then the initial calculated value would be divided by 10,000, then multiplied by 1,000 and rounded per the convention.  The result of this would then be divided by 1,000 and multiplied by 10,000 to get the final value.
    precision: 0,  // optional — The precision of the rounding.  The decimal places to which the rounding takes place.  Defaults to 0 if not set.
    roundingTarget: "...",  // optional — The target of the rounding convention.  Accepted values are &#39;AccruedInterest&#39;, &#39;Cashflows&#39;, or &#39;All&#39;    Supported string (enumeration) values are: [All, AccruedInterest, Cashflows].  Defaults to \&quot;All\&quot; if not set.
    roundingType: "..."  // optional — The type of rounding.  e.g. Round Up, Round Down    Supported string (enumeration) values are: [Down, Up, Floor, Ceiling, Nearest].  Defaults to \&quot;Nearest\&quot; if not set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RoundingConvention>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

