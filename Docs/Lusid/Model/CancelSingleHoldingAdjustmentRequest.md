# Finbourne.Sdk.Lusid.Model.CancelSingleHoldingAdjustmentRequest

This request specifies single target holding. i.e. holding data that the  system should match. And deletes previous adjustment made to that holding
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | A set of instrument identifiers that can resolve the holding adjustment to a unique instrument. |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The sub-holding properties which identify the holding. Each property must be from the &#39;Transaction&#39; domain. |
| **Currency** | **string** | Optional | The Holding currency. |
| **CustodianAccountId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CancelSingleHoldingAdjustmentRequest(
    instrumentIdentifiers: ,  // required — A set of instrument identifiers that can resolve the holding adjustment to a unique instrument.
    subHoldingKeys: new PerpetualProperty(...),  // optional — The sub-holding properties which identify the holding. Each property must be from the &#39;Transaction&#39; domain.
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
var instance = JsonConvert.DeserializeObject<CancelSingleHoldingAdjustmentRequest>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

