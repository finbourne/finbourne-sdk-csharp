# Finbourne.Sdk.Lusid.Model.HoldingAdjustmentWithDate

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset** | Optional | The effective date of the holding adjustment |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Optional | A set of instrument identifiers that can resolve the holding adjustment to a unique instrument. |
| **InstrumentScope** | **string** | Optional | The scope of the instrument that the holding adjustment is in. |
| **InstrumentUid** | **string** | Required | The unique Lusid Instrument Id (LUID) of the instrument that the holding adjustment is in. |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The set of unique transaction properties and associated values stored with the holding adjustment transactions automatically created by LUSID. Each property will be from the &#39;Transaction&#39; domain. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The set of unique holding properties and associated values stored with the target holding. Each property will be from the &#39;Holding&#39; domain. |
| **TaxLots** | [List&lt;TargetTaxLot&gt;](TargetTaxLot.md) | Required | The tax-lots that together make up the target holding. |
| **Currency** | **string** | Optional | The Holding currency. |
| **CustodianAccountId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new HoldingAdjustmentWithDate(
    effectiveAt: DateTimeOffset.Now,  // optional — The effective date of the holding adjustment
    instrumentIdentifiers: ,  // optional — A set of instrument identifiers that can resolve the holding adjustment to a unique instrument.
    instrumentScope: "...",  // optional — The scope of the instrument that the holding adjustment is in.
    instrumentUid: "...",  // required — The unique Lusid Instrument Id (LUID) of the instrument that the holding adjustment is in.
    subHoldingKeys: new PerpetualProperty(...),  // optional — The set of unique transaction properties and associated values stored with the holding adjustment transactions automatically created by LUSID. Each property will be from the &#39;Transaction&#39; domain.
    properties: new PerpetualProperty(...),  // optional — The set of unique holding properties and associated values stored with the target holding. Each property will be from the &#39;Holding&#39; domain.
    taxLots: new List<TargetTaxLot>(),  // required — The tax-lots that together make up the target holding.
    currency: "...",  // optional — The Holding currency.
    custodianAccountId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HoldingAdjustmentWithDate>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [TargetTaxLot](TargetTaxLot.md) — used in `TaxLots`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

