# Finbourne.Sdk.Lusid.Model.Facility

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **FacilityCode** | **string** | Optional | The code of the Facility, unique within the Fund. |
| **DisplayName** | **string** | Required | The name of the Facility. |
| **Description** | **string** | Optional | A description for the Facility. |
| **Lender** | **string** | Required | The name of the lender providing the Facility. |
| **Limit** | **decimal** | Required | The committed limit of the Facility. Must be greater than zero. |
| **Currency** | **string** | Required | The three-letter currency code in which the Facility is denominated. |
| **RateReference** | **string** | Optional | The reference rate the Facility interest is based on, for example SOFR. Optional. |
| **Margin** | **decimal** | Required | The margin over the reference rate, expressed as a decimal. Must be zero or greater. |
| **CommitmentFeeRate** | **decimal** | Required | The annual commitment fee rate charged on the undrawn balance, expressed as a decimal. Must be zero or greater. |
| **DayCountConvention** | **string** | Required | The day count convention used to accrue interest. One of: Act360, Act365, Act365F, Thirty360. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Facility(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    facilityCode: "...",  // optional — The code of the Facility, unique within the Fund.
    displayName: "...",  // required — The name of the Facility.
    description: "...",  // optional — A description for the Facility.
    lender: "...",  // required — The name of the lender providing the Facility.
    limit: 0.0d,  // required — The committed limit of the Facility. Must be greater than zero.
    currency: "...",  // required — The three-letter currency code in which the Facility is denominated.
    rateReference: "...",  // optional — The reference rate the Facility interest is based on, for example SOFR. Optional.
    margin: 0.0d,  // required — The margin over the reference rate, expressed as a decimal. Must be zero or greater.
    commitmentFeeRate: 0.0d,  // required — The annual commitment fee rate charged on the undrawn balance, expressed as a decimal. Must be zero or greater.
    dayCountConvention: "...",  // required — The day count convention used to accrue interest. One of: Act360, Act365, Act365F, Thirty360.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Facility>(json);
```

- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

