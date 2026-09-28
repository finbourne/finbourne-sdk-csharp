# Finbourne.Sdk.Lusid.Model.ComplianceRuleContribution

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Index** | **int** | Required | The position of this contribution within the compliance run. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **OrderId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Instrument** | **string** | Required | The LUSID instrument identifier (LUID) of the instrument for this contribution. |
| **InstrumentType** | **string** | Optional | Optional. The economic type of the instrument for this contribution. |
| **HoldingType** | **string** | Optional | Optional. The holding type of this contribution. |
| **HoldingId** | **string** | Optional | Optional. The internal holding identifier encoding the detail of what the holding includes. |
| **ResultValues** | **Dictionary&lt;string, decimal&gt;** | Required | Dictionary of AddressKey (as string) and their corresponding decimal valuation results for this contribution. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Required | Dictionary of PropertyKey (as string) and their corresponding property for this contribution. |
| **RelatedProperties** | **Dictionary&lt;string, string&gt;** | Required | Dictionary of related property keys (as string) and their string values, read from related entities across a relationship. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleContribution(
    index: 0,  // required — The position of this contribution within the compliance run.
    portfolioId: new ResourceId(...),  // required
    orderId: new ResourceId(...),  // optional
    instrument: "...",  // required — The LUSID instrument identifier (LUID) of the instrument for this contribution.
    instrumentType: "...",  // optional — Optional. The economic type of the instrument for this contribution.
    holdingType: "...",  // optional — Optional. The holding type of this contribution.
    holdingId: "...",  // optional — Optional. The internal holding identifier encoding the detail of what the holding includes.
    resultValues: ,  // required — Dictionary of AddressKey (as string) and their corresponding decimal valuation results for this contribution.
    properties: new Property(...),  // required — Dictionary of PropertyKey (as string) and their corresponding property for this contribution.
    relatedProperties:   // required — Dictionary of related property keys (as string) and their string values, read from related entities across a relationship.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleContribution>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

