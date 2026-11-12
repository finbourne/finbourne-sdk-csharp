# Finbourne.Sdk.Lusid.Model.TaxClassificationInputs

The instrument static the decision tree reads. A missing flag is a missing input, not a false.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LoanRelationshipAsset** | **bool?** | Optional | Whether the instrument is a loan relationship asset. |
| **IndexLinkedGilt** | **bool?** | Optional | Whether the instrument is an index-linked gilt. |
| **ChargeableAsset** | **bool?** | Optional | Whether disposals of the instrument give rise to chargeable gains. |
| **CisNonTransparent** | **bool?** | Optional | Whether the instrument is a non-transparent collective investment scheme. |
| **CisTransparent** | **bool?** | Optional | Whether the instrument is a transparent collective investment scheme. |
| **Derivative** | **bool?** | Optional | Whether the instrument is a derivative contract. |
| **DerivativeFinancialFuture** | **bool?** | Optional | Whether the derivative is a financial future or option within the chargeable gains rules. |
| **DerivativePooledSecurity** | **bool?** | Optional | Whether the derivative is pooled as a security. |
| **PrivateEquity** | **bool?** | Optional | Whether the instrument is a private equity holding. |
| **RealEstate** | **bool?** | Optional | Whether the instrument is a real estate holding. |
| **QualifyingInvestmentsPercent** | **decimal?** | Optional | The percentage of the scheme&#39;s assets that are qualifying (non-equity) investments; more than 60 percent makes the scheme a bond fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxClassificationInputs(
    loanRelationshipAsset: true,  // optional — Whether the instrument is a loan relationship asset.
    indexLinkedGilt: true,  // optional — Whether the instrument is an index-linked gilt.
    chargeableAsset: true,  // optional — Whether disposals of the instrument give rise to chargeable gains.
    cisNonTransparent: true,  // optional — Whether the instrument is a non-transparent collective investment scheme.
    cisTransparent: true,  // optional — Whether the instrument is a transparent collective investment scheme.
    derivative: true,  // optional — Whether the instrument is a derivative contract.
    derivativeFinancialFuture: true,  // optional — Whether the derivative is a financial future or option within the chargeable gains rules.
    derivativePooledSecurity: true,  // optional — Whether the derivative is pooled as a security.
    privateEquity: true,  // optional — Whether the instrument is a private equity holding.
    realEstate: true,  // optional — Whether the instrument is a real estate holding.
    qualifyingInvestmentsPercent: 0.0d  // optional — The percentage of the scheme&#39;s assets that are qualifying (non-equity) investments; more than 60 percent makes the scheme a bond fund.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxClassificationInputs>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

