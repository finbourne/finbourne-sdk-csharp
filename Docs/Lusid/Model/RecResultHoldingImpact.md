# Finbourne.Sdk.Lusid.Model.RecResultHoldingImpact

One holding, and where known the tax lot within it, that a transaction or settlement activity item impacted.  Also holds the display names of the holding's instrument.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HoldingId** | **string** | Required | The impacted holding, at holding level: the id a holding item over it carries. |
| **TaxLotId** | **string** | Optional | The impacted tax lot within the holding, where the source states one; null when the impact is known at holding level only. Opaque: compare it whole, do not parse it. |
| **HoldingInstrumentScope** | **string** | Optional | The scope of the impacted holding&#39;s instrument. Null where the source does not state one. |
| **HoldingLusidInstrumentId** | **string** | Optional | The LUID of the impacted holding&#39;s instrument. Null where the source does not state it. |
| **HoldingInstrumentName** | **string** | Optional | The name of the impacted holding&#39;s instrument, as it stood at the asAt the run read its data. Null where the run did not resolve it. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultHoldingImpact(
    holdingId: "...",  // required — The impacted holding, at holding level: the id a holding item over it carries.
    taxLotId: "...",  // optional — The impacted tax lot within the holding, where the source states one; null when the impact is known at holding level only. Opaque: compare it whole, do not parse it.
    holdingInstrumentScope: "...",  // optional — The scope of the impacted holding&#39;s instrument. Null where the source does not state one.
    holdingLusidInstrumentId: "...",  // optional — The LUID of the impacted holding&#39;s instrument. Null where the source does not state it.
    holdingInstrumentName: "..."  // optional — The name of the impacted holding&#39;s instrument, as it stood at the asAt the run read its data. Null where the run did not resolve it.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultHoldingImpact>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

