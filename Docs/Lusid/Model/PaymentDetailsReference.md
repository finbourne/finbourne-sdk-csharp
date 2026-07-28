# Finbourne.Sdk.Lusid.Model.PaymentDetailsReference

A pointer to a Payment Details relational dataset series for a payor or payee entity.  No PII is stored here — bank account details are resolved at read time from the referenced series.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SeriesScope** | **string** | Required | The scope of the relational datapoint. May differ from the scope of the dataset definition. |
| **ApplicableEntity** | [PaymentDetailsApplicableEntity](PaymentDetailsApplicableEntity.md) | Required | *No description available.* |
| **SeriesIdentifiers** | [PaymentDetailsSeriesIdentifiers](PaymentDetailsSeriesIdentifiers.md) | Required | *No description available.* |
| **EffectiveDate** | **DateTimeOffset** | Required | The effective date of the relational datapoint observation to retrieve. ISO 8601 datetime. |
| **AsAtDate** | **DateTimeOffset** | Required | The as-at date of the relational datapoint observation to retrieve. ISO 8601 datetime. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PaymentDetailsReference(
    seriesScope: "...",  // required — The scope of the relational datapoint. May differ from the scope of the dataset definition.
    applicableEntity: new PaymentDetailsApplicableEntity(...),  // required
    seriesIdentifiers: new PaymentDetailsSeriesIdentifiers(...),  // required
    effectiveDate: DateTimeOffset.Now,  // required — The effective date of the relational datapoint observation to retrieve. ISO 8601 datetime.
    asAtDate: DateTimeOffset.Now  // required — The as-at date of the relational datapoint observation to retrieve. ISO 8601 datetime.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PaymentDetailsReference>(json);
```

- [PaymentDetailsApplicableEntity](PaymentDetailsApplicableEntity.md)
- [PaymentDetailsSeriesIdentifiers](PaymentDetailsSeriesIdentifiers.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

