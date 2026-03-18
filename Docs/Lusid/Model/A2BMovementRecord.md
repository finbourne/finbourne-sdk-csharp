# Finbourne.Sdk.Lusid.Model.A2BMovementRecord

A2B Movement Record - shows A2B category based changes relating to a specific movement
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **HoldingType** | **string** | Optional | The code for the type of the holding e.g. P, B, C, R, F etc. |
| **InstrumentScope** | **string** | Optional | The unique Lusid Instrument Id (LUID) of the instrument that the holding is in. |
| **InstrumentUid** | **string** | Optional | The unique Lusid Instrument Id (LUID) of the instrument that the holding is in. |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The sub-holding properties which identify the holding. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio. |
| **Currency** | **string** | Optional | The holding currency. |
| **TransactionId** | **string** | Optional | The unique identifier for the transaction. |
| **MovementName** | **string** | Optional | The name of the movement. |
| **EffectiveDate** | **DateTimeOffset** | Optional | The date of the movement. |
| **Units** | **decimal** | Optional | The number of units of the instrument that are affected by the movement. |
| **Start** | [A2BCategory](A2BCategory.md) | Optional | *No description available.* |
| **Flows** | [A2BCategory](A2BCategory.md) | Optional | *No description available.* |
| **Gains** | [A2BCategory](A2BCategory.md) | Optional | *No description available.* |
| **Carry** | [A2BCategory](A2BCategory.md) | Optional | *No description available.* |
| **End** | [A2BCategory](A2BCategory.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The properties which have been requested to be decorated onto the holding. These will be from the &#39;Instrument&#39; domain. |
| **GroupId** | **string** | Optional | Arbitrary string that can be used to cross reference an entry in the A2B report with activity in the A2B-Movements. This should be used purely as a token. The content should not be relied upon. |
| **Errors** | [List&lt;ResponseMetaData&gt;](ResponseMetaData.md) | Optional | Any errors with the record are reported here. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new A2BMovementRecord(
    portfolioId: new ResourceId(...),  // optional
    holdingType: "...",  // optional — The code for the type of the holding e.g. P, B, C, R, F etc.
    instrumentScope: "...",  // optional — The unique Lusid Instrument Id (LUID) of the instrument that the holding is in.
    instrumentUid: "...",  // optional — The unique Lusid Instrument Id (LUID) of the instrument that the holding is in.
    subHoldingKeys: new PerpetualProperty(...),  // optional — The sub-holding properties which identify the holding. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio.
    currency: "...",  // optional — The holding currency.
    transactionId: "...",  // optional — The unique identifier for the transaction.
    movementName: "...",  // optional — The name of the movement.
    effectiveDate: DateTimeOffset.Now,  // optional — The date of the movement.
    units: 0.0d,  // optional — The number of units of the instrument that are affected by the movement.
    start: new A2BCategory(...),  // optional
    flows: new A2BCategory(...),  // optional
    gains: new A2BCategory(...),  // optional
    carry: new A2BCategory(...),  // optional
    end: new A2BCategory(...),  // optional
    properties: new Property(...),  // optional — The properties which have been requested to be decorated onto the holding. These will be from the &#39;Instrument&#39; domain.
    groupId: "...",  // optional — Arbitrary string that can be used to cross reference an entry in the A2B report with activity in the A2B-Movements. This should be used purely as a token. The content should not be relied upon.
    errors: new List<ResponseMetaData>()  // optional — Any errors with the record are reported here.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<A2BMovementRecord>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [A2BCategory](A2BCategory.md)
- [A2BCategory](A2BCategory.md)
- [A2BCategory](A2BCategory.md)
- [A2BCategory](A2BCategory.md)
- [A2BCategory](A2BCategory.md)
- [Property](Property.md) — used in `Properties`
- [ResponseMetaData](ResponseMetaData.md) — used in `Errors`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

