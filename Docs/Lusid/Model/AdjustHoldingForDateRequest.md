# Finbourne.Sdk.Lusid.Model.AdjustHoldingForDateRequest

This request specifies target holdings. i.e. holding data that the  system should match. When processed by the movement  engine, it will create 'true-up' adjustments on the fly.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The Effective date that the target holding will be adjusted at. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | A set of instrument identifiers that can resolve the holding adjustment to a unique instrument. |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Set of unique transaction properties and associated values to store with the holding adjustment transaction automatically created by LUSID. Each property must be from the &#39;Transaction&#39; domain. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Set of unique holding properties and associated values to store with the target holding. Each property must be from the &#39;Holding&#39; domain. |
| **TaxLots** | [List&lt;TargetTaxLotRequest&gt;](TargetTaxLotRequest.md) | Required | The tax-lots that together make up the target holding. |
| **Currency** | **string** | Optional | The Holding currency. This needs to be equal with the one on the TaxLot -&gt; cost if one is specified |
| **CustodianAccountId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AdjustHoldingForDateRequest(
    effectiveAt: new DateTimeOrCutLabel(...),  // required — The Effective date that the target holding will be adjusted at.
    instrumentIdentifiers: ,  // required — A set of instrument identifiers that can resolve the holding adjustment to a unique instrument.
    subHoldingKeys: new PerpetualProperty(...),  // optional — Set of unique transaction properties and associated values to store with the holding adjustment transaction automatically created by LUSID. Each property must be from the &#39;Transaction&#39; domain.
    properties: new PerpetualProperty(...),  // optional — Set of unique holding properties and associated values to store with the target holding. Each property must be from the &#39;Holding&#39; domain.
    taxLots: new List<TargetTaxLotRequest>(),  // required — The tax-lots that together make up the target holding.
    currency: "...",  // optional — The Holding currency. This needs to be equal with the one on the TaxLot -&gt; cost if one is specified
    custodianAccountId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AdjustHoldingForDateRequest>(json);
```


## Related Models

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`
- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [TargetTaxLotRequest](TargetTaxLotRequest.md) — used in `TaxLots`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

