# Finbourne.Sdk.Lusid.Model.CounterpartyRiskInformation

In the event that the legal entity is a counterparty to an OTC transaction  (as signatory to a counterparty agreement such as an ISDA 2002 Master Agreement),  this information would be needed for calculations  such as Credit-Valuation-Adjustments and Debit-Valuation-Adjustments (CVA, DVA, XVA etc).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CountryOfRisk** | **string** | Required | The country to which one would naturally ascribe risk, typically the legal entity&#39;s country of registration. This can be used to infer funding currency and related market data in the absence of a specific preference. |
| **CreditRatings** | [List&lt;CreditRating&gt;](CreditRating.md) | Required | *No description available.* |
| **IndustryClassifiers** | [List&lt;IndustryClassifier&gt;](IndustryClassifier.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CounterpartyRiskInformation(
    countryOfRisk: "...",  // required — The country to which one would naturally ascribe risk, typically the legal entity&#39;s country of registration. This can be used to infer funding currency and related market data in the absence of a specific preference.
    creditRatings: new List<CreditRating>(),  // required
    industryClassifiers: new List<IndustryClassifier>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CounterpartyRiskInformation>(json);
```

- [CreditRating](CreditRating.md)
- [IndustryClassifier](IndustryClassifier.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

