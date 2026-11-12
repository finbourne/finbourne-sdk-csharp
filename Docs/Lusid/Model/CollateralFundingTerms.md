# Finbourne.Sdk.Lusid.Model.CollateralFundingTerms

What margin posted under the agreement costs us: the annual rate it is funded at, the basis it accrues on and the  lending fee assumed forgone on a security with no fee quote of its own when collateral is ranked.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Rate** | **decimal** | Required | The annual rate posted margin is funded at, as a fraction, for example 0.053 for 5.3%. Between -1 and 1. |
| **DayCountBasis** | **int** | Required | The number of days in the year the funding rate accrues over. Either 360 or 365. |
| **DefaultLendingFee** | **decimal?** | Optional | The annual lending fee, as a fraction, assumed forgone on a security with no fee quote of its own when collateral is ranked. Between 0 and 1. A security with no fee at all cannot be ranked. Optional. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CollateralFundingTerms(
    rate: 0.0d,  // required — The annual rate posted margin is funded at, as a fraction, for example 0.053 for 5.3%. Between -1 and 1.
    dayCountBasis: 0,  // required — The number of days in the year the funding rate accrues over. Either 360 or 365.
    defaultLendingFee: 0.0d  // optional — The annual lending fee, as a fraction, assumed forgone on a security with no fee quote of its own when collateral is ranked. Between 0 and 1. A security with no fee at all cannot be ranked. Optional.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CollateralFundingTerms>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

