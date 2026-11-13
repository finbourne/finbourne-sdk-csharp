# Finbourne.Sdk.Lusid.Model.ComplianceRuleContribution

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **OrderId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Instrument** | **string** | Required | The LUSID instrument identifier (LUID) of the instrument for this contribution. |
| **InstrumentType** | **string** | Optional | Optional. The economic type of the instrument for this contribution. |
| **HoldingType** | **string** | Optional | Optional. The holding type of this contribution. |
| **HoldingId** | **string** | Optional | Optional. The internal holding identifier encoding the detail of what the holding includes. |
| **HeldBy** | **string** | Optional | Optional. Where this holding sits relative to the rule&#39;s benchmark: portfolio, benchmark or both.  Meaningful only for benchmark-relative rules. |
| **KeysUsed** | [List&lt;ComplianceKeyUsed&gt;](ComplianceKeyUsed.md) | Required | The keys this holding contributed to the rule: each key the rule read (plus the portfolio NAV key), with the  role(s) it played, the holding&#39;s own value for it, and which bag the value came from. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleContribution(
    portfolioId: new ResourceId(...),  // required
    orderId: new ResourceId(...),  // optional
    instrument: "...",  // required — The LUSID instrument identifier (LUID) of the instrument for this contribution.
    instrumentType: "...",  // optional — Optional. The economic type of the instrument for this contribution.
    holdingType: "...",  // optional — Optional. The holding type of this contribution.
    holdingId: "...",  // optional — Optional. The internal holding identifier encoding the detail of what the holding includes.
    heldBy: "...",  // optional — Optional. Where this holding sits relative to the rule&#39;s benchmark: portfolio, benchmark or both.  Meaningful only for benchmark-relative rules.
    keysUsed: new List<ComplianceKeyUsed>()  // required — The keys this holding contributed to the rule: each key the rule read (plus the portfolio NAV key), with the  role(s) it played, the holding&#39;s own value for it, and which bag the value came from.
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


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ComplianceKeyUsed](ComplianceKeyUsed.md) — used in `KeysUsed`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

