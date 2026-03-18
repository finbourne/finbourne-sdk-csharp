# Finbourne.Sdk.Lusid.Model.CalculationInfo

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CalculationMethod** | **string** | Required | Method of calculating the fees or commission among: BasisPoints, Percentage, Rate, Flat etc. |
| **Multiplier** | **string** | Required | Field by which to multiply the numerical amount. Eg: Quantity, Value |
| **CalculationAmount** | **decimal** | Required | Numerical fee amount |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CalculationInfo(
    calculationMethod: "...",  // required — Method of calculating the fees or commission among: BasisPoints, Percentage, Rate, Flat etc.
    multiplier: "...",  // required — Field by which to multiply the numerical amount. Eg: Quantity, Value
    calculationAmount: 0.0d  // required — Numerical fee amount
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CalculationInfo>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

