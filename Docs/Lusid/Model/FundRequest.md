# Finbourne.Sdk.Lusid.Model.FundRequest

The request used to create a Fund.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code given for the Fund. |
| **DisplayName** | **string** | Optional | The name of the Fund. |
| **Description** | **string** | Optional | A description for the Fund. |
| **FundConfigurationId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **AborId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ShareClassInstrumentScopes** | **List&lt;string&gt;** | Optional | The scopes in which the instruments lie, currently limited to one. |
| **ShareClassInstruments** | [List&lt;InstrumentResolutionDetail&gt;](InstrumentResolutionDetail.md) | Optional | Details the user-provided instrument identifiers and the instrument resolved from them. |
| **Type** | **string** | Required | The type of fund; &#39;Standalone&#39;, &#39;Master&#39; or &#39;Feeder&#39; |
| **InceptionDate** | **DateTimeOffset** | Required | Inception date of the Fund |
| **DecimalPlaces** | **int?** | Optional | Number of decimal places for reporting |
| **YearEndDate** | [DayMonth](DayMonth.md) | Required | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundRequest(
    code: "...",  // required — The code given for the Fund.
    displayName: "...",  // optional — The name of the Fund.
    description: "...",  // optional — A description for the Fund.
    fundConfigurationId: new ResourceId(...),  // required
    aborId: new ResourceId(...),  // required
    shareClassInstrumentScopes: ,  // optional — The scopes in which the instruments lie, currently limited to one.
    shareClassInstruments: new List<InstrumentResolutionDetail>(),  // optional — Details the user-provided instrument identifiers and the instrument resolved from them.
    type: "...",  // required — The type of fund; &#39;Standalone&#39;, &#39;Master&#39; or &#39;Feeder&#39;
    inceptionDate: DateTimeOffset.Now,  // required — Inception date of the Fund
    decimalPlaces: 0,  // optional — Number of decimal places for reporting
    yearEndDate: new DayMonth(...),  // required
    properties: new Property(...)  // optional — A set of properties for the Fund.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundRequest>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [InstrumentResolutionDetail](InstrumentResolutionDetail.md) — used in `ShareClassInstruments`
- [DayMonth](DayMonth.md)
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

