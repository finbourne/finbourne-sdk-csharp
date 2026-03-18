# Finbourne.Sdk.Lusid.Model.ModelSelection

The combination of a library to use and a model in that library that defines which pricing code will evaluate instruments  having a particular type/class. This allows us to control the model type and library for a given instrument.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Library** | **string** | Required | The available values are: Lusid, RefinitivQps, RefinitivTracsWeb, VolMaster, IsdaCds, YieldBook, LusidCalc |
| **Model** | **string** | Required | The available values are: SimpleStatic, Discounting, VendorDefault, BlackScholes, ConstantTimeValueOfMoney, Bachelier, ForwardWithPoints, ForwardWithPointsUndiscounted, ForwardSpecifiedRate, ForwardSpecifiedRateUndiscounted, IndexNav, IndexPrice, InlinedIndex, ForwardFromCurve, ForwardFromCurveUndiscounted, BlackScholesDigital, BjerksundStensland1993, BondLookupPricer, FlexibleLoanPricer, CdsLookupPricer, LoanFacilityPricer, OverrideOnlyPricer, FlexibleRepoSimplePricer |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ModelSelection(
    library: "...",  // required — The available values are: Lusid, RefinitivQps, RefinitivTracsWeb, VolMaster, IsdaCds, YieldBook, LusidCalc
    model: "..."  // required — The available values are: SimpleStatic, Discounting, VendorDefault, BlackScholes, ConstantTimeValueOfMoney, Bachelier, ForwardWithPoints, ForwardWithPointsUndiscounted, ForwardSpecifiedRate, ForwardSpecifiedRateUndiscounted, IndexNav, IndexPrice, InlinedIndex, ForwardFromCurve, ForwardFromCurveUndiscounted, BlackScholesDigital, BjerksundStensland1993, BondLookupPricer, FlexibleLoanPricer, CdsLookupPricer, LoanFacilityPricer, OverrideOnlyPricer, FlexibleRepoSimplePricer
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ModelSelection>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

