# Finbourne.Sdk.Lusid.Model.QualifyingInvestmentsHistory

The daily qualifying-investments history of one collective investment scheme and the flips within it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Luid** | **string** | Required | The LUSID instrument identifier of the collective investment scheme. |
| **ThresholdPercent** | **decimal** | Required | The qualifying investments percentage the scheme must exceed to be a bond fund. |
| **Observations** | [List&lt;QualifyingInvestmentsObservation&gt;](QualifyingInvestmentsObservation.md) | Required | The daily qualifying investments observations in the requested window, oldest first. |
| **Crossings** | [List&lt;QualifyingInvestmentsCrossing&gt;](QualifyingInvestmentsCrossing.md) | Required | Each pair of consecutive observations where the bond fund result flipped. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QualifyingInvestmentsHistory(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    luid: "...",  // required — The LUSID instrument identifier of the collective investment scheme.
    thresholdPercent: 0.0d,  // required — The qualifying investments percentage the scheme must exceed to be a bond fund.
    observations: new List<QualifyingInvestmentsObservation>(),  // required — The daily qualifying investments observations in the requested window, oldest first.
    crossings: new List<QualifyingInvestmentsCrossing>(),  // required — Each pair of consecutive observations where the bond fund result flipped.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QualifyingInvestmentsHistory>(json);
```

- [QualifyingInvestmentsObservation](QualifyingInvestmentsObservation.md) — used in `Observations`
- [QualifyingInvestmentsCrossing](QualifyingInvestmentsCrossing.md) — used in `Crossings`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

