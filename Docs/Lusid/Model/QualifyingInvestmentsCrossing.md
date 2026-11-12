# Finbourne.Sdk.Lusid.Model.QualifyingInvestmentsCrossing

A flip of the qualifying-investments result between two consecutive observed days.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **From** | **DateTimeOffset** | Required | The date of the observation before the flip. |
| **To** | **DateTimeOffset** | Required | The date of the observation after the flip. |
| **WasBondFundBefore** | **bool** | Required | Whether the scheme was a bond fund on the From date. |
| **IsBondFundAfter** | **bool** | Required | Whether the scheme was a bond fund on the To date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QualifyingInvestmentsCrossing(
    from: DateTimeOffset.Now,  // required — The date of the observation before the flip.
    to: DateTimeOffset.Now,  // required — The date of the observation after the flip.
    wasBondFundBefore: true,  // required — Whether the scheme was a bond fund on the From date.
    isBondFundAfter: true  // required — Whether the scheme was a bond fund on the To date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QualifyingInvestmentsCrossing>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

