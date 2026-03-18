# Finbourne.Sdk.Lusid.Model.CreditSupportAnnex

Entity to capture the calculable and queryable methods and practices of determining and transferring collateral  to a counterparty as part of margining of transactions. These typically come from a particular ISDA agreement  that is in place between the two counterparties.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ReferenceCurrency** | **string** | Required | The base, or reference, currency against which MtM value and exposure should be calculated  and in which the CSA parameters are defined if the currency is not otherwise explicitly stated. |
| **CollateralCurrencies** | **List&lt;string&gt;** | Required | The set of currencies within which it is acceptable to post cash collateral. |
| **IsdaAgreementVersion** | **string** | Required | The transactions will take place with reference to a particular ISDA master agreement. This  will likely be either the ISDA 1992 or ISDA 2002 agremeents or ISDA close-out 2009. |
| **MarginCallFrequency** | **string** | Required | The tenor, e.g. daily (1D) or biweekly (2W), at which frequency a margin call will be made, calculations  made and money transferred to readjust. The calculation might also require a specific time for valuation and notification. |
| **ValuationAgent** | **string** | Required | Are the calculations performed by the institutions&#39;s counterparty or the institution trading with them. |
| **ThresholdAmount** | **decimal** | Required | At what level of exposure does collateral need to be posted. Will typically be zero for banks.  Should be stated in reference currency |
| **RoundingDecimalPlaces** | **int** | Required | Where a calculation needs to be rounded to a specific number of decimal places,  this states the number that that requires. |
| **InitialMarginAmount** | **decimal** | Required | The initial margin that is required. In the reference currency |
| **MinimumTransferAmount** | **decimal** | Required | The minimum amount, in the reference currency, that must be transferred when required. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreditSupportAnnex(
    referenceCurrency: "...",  // required — The base, or reference, currency against which MtM value and exposure should be calculated  and in which the CSA parameters are defined if the currency is not otherwise explicitly stated.
    collateralCurrencies: ,  // required — The set of currencies within which it is acceptable to post cash collateral.
    isdaAgreementVersion: "...",  // required — The transactions will take place with reference to a particular ISDA master agreement. This  will likely be either the ISDA 1992 or ISDA 2002 agremeents or ISDA close-out 2009.
    marginCallFrequency: "...",  // required — The tenor, e.g. daily (1D) or biweekly (2W), at which frequency a margin call will be made, calculations  made and money transferred to readjust. The calculation might also require a specific time for valuation and notification.
    valuationAgent: "...",  // required — Are the calculations performed by the institutions&#39;s counterparty or the institution trading with them.
    thresholdAmount: 0.0d,  // required — At what level of exposure does collateral need to be posted. Will typically be zero for banks.  Should be stated in reference currency
    roundingDecimalPlaces: 0,  // required — Where a calculation needs to be rounded to a specific number of decimal places,  this states the number that that requires.
    initialMarginAmount: 0.0d,  // required — The initial margin that is required. In the reference currency
    minimumTransferAmount: 0.0d,  // required — The minimum amount, in the reference currency, that must be transferred when required.
    id: new ResourceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreditSupportAnnex>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

