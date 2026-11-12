# Finbourne.Sdk.Lusid.Model.TaxClassification

The UK life-company tax classification of one instrument at one effective and asAt point.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Luid** | **string** | Required | The LUSID instrument identifier of the classified instrument. |
| **InstrumentName** | **string** | Optional | The name of the classified instrument. |
| **InstrumentType** | **string** | Optional | The LUSID instrument type of the classified instrument, where known. |
| **WithinBlagab** | **bool?** | Optional | Whether the instrument is held within the basic life assurance and general annuity business of the fund. Absent when the input has not been set. |
| **Inputs** | [TaxClassificationInputs](TaxClassificationInputs.md) | Required | *No description available.* |
| **TreatmentOverride** | **string** | Optional | The user-supplied treatment leaf that replaces the system-derived one, if any. Available values: OutsideBlagab, LoanRelationship, IndexLinkedGilt, PrivateEquity, RealEstate, FinancialFuture, PooledDerivative, DerivativeProfitAndLoss, NonTransparentScheme, BondFund, TransparentScheme, StandardEquity, Exempt. |
| **Leaf** | **string** | Optional | The treatment leaf the decision tree arrived at. Absent when the instrument could not be classified. Available values: OutsideBlagab, LoanRelationship, IndexLinkedGilt, PrivateEquity, RealEstate, FinancialFuture, PooledDerivative, DerivativeProfitAndLoss, NonTransparentScheme, BondFund, TransparentScheme, StandardEquity, Exempt. |
| **Treatment** | **string** | Required | The tax treatment class implied by the leaf: ChargeableGains, LoanRelationship, Excluded or Unclassified. Available values: ChargeableGains, LoanRelationship, Excluded, Unclassified. |
| **Status** | **string** | Required | Classified, Overridden, Rejected or Unclassified. Available values: Classified, Overridden, Rejected, Unclassified. |
| **Source** | **string** | Required | Whether the leaf came from the System decision tree or a User override. Available values: System, User. |
| **RuleFired** | **string** | Required | The name of the decision-tree rule that produced the leaf. |
| **Trace** | [List&lt;TaxClassificationDecisionStep&gt;](TaxClassificationDecisionStep.md) | Optional | The ordered questions the decision tree asked and the answers it took, for audit. |
| **Exception** | [TaxClassificationException](TaxClassificationException.md) | Optional | *No description available.* |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective date the classification was evaluated at. |
| **AsAt** | **DateTimeOffset** | Required | The asAt time the classification was evaluated at. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxClassification(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    luid: "...",  // required — The LUSID instrument identifier of the classified instrument.
    instrumentName: "...",  // optional — The name of the classified instrument.
    instrumentType: "...",  // optional — The LUSID instrument type of the classified instrument, where known.
    withinBlagab: true,  // optional — Whether the instrument is held within the basic life assurance and general annuity business of the fund. Absent when the input has not been set.
    inputs: new TaxClassificationInputs(...),  // required
    treatmentOverride: "...",  // optional — The user-supplied treatment leaf that replaces the system-derived one, if any. Available values: OutsideBlagab, LoanRelationship, IndexLinkedGilt, PrivateEquity, RealEstate, FinancialFuture, PooledDerivative, DerivativeProfitAndLoss, NonTransparentScheme, BondFund, TransparentScheme, StandardEquity, Exempt.
    leaf: "...",  // optional — The treatment leaf the decision tree arrived at. Absent when the instrument could not be classified. Available values: OutsideBlagab, LoanRelationship, IndexLinkedGilt, PrivateEquity, RealEstate, FinancialFuture, PooledDerivative, DerivativeProfitAndLoss, NonTransparentScheme, BondFund, TransparentScheme, StandardEquity, Exempt.
    treatment: "...",  // required — The tax treatment class implied by the leaf: ChargeableGains, LoanRelationship, Excluded or Unclassified. Available values: ChargeableGains, LoanRelationship, Excluded, Unclassified.
    status: "...",  // required — Classified, Overridden, Rejected or Unclassified. Available values: Classified, Overridden, Rejected, Unclassified.
    source: "...",  // required — Whether the leaf came from the System decision tree or a User override. Available values: System, User.
    ruleFired: "...",  // required — The name of the decision-tree rule that produced the leaf.
    trace: new List<TaxClassificationDecisionStep>(),  // optional — The ordered questions the decision tree asked and the answers it took, for audit.
    exception: new TaxClassificationException(...),  // optional
    effectiveAt: DateTimeOffset.Now,  // required — The effective date the classification was evaluated at.
    asAt: DateTimeOffset.Now,  // required — The asAt time the classification was evaluated at.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxClassification>(json);
```

- [TaxClassificationInputs](TaxClassificationInputs.md)
- [TaxClassificationDecisionStep](TaxClassificationDecisionStep.md) — used in `Trace`
- [TaxClassificationException](TaxClassificationException.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

