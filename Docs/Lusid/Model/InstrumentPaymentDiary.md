# Finbourne.Sdk.Lusid.Model.InstrumentPaymentDiary

A payment diary containing all the cashflows on a single instrument.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentIdType** | **string** | Optional | The identifier type of the instrument. |
| **InstrumentId** | **string** | Optional | The identifier for the instrument. |
| **InstrumentScope** | **string** | Optional | The scope of the instrument. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Legs** | [List&lt;InstrumentPaymentDiaryLeg&gt;](InstrumentPaymentDiaryLeg.md) | Optional | Aggregated sets of Cashflows. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentPaymentDiary(
    instrumentIdType: "...",  // optional — The identifier type of the instrument.
    instrumentId: "...",  // optional — The identifier for the instrument.
    instrumentScope: "...",  // optional — The scope of the instrument.
    varVersion: new ModelVersion(...),  // optional
    legs: new List<InstrumentPaymentDiaryLeg>(),  // optional — Aggregated sets of Cashflows.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentPaymentDiary>(json);
```

- [ModelVersion](ModelVersion.md)
- [InstrumentPaymentDiaryLeg](InstrumentPaymentDiaryLeg.md) — used in `Legs`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

