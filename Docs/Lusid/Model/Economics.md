# Finbourne.Sdk.Lusid.Model.Economics

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentScope** | **string** | Optional | The scope in which the instrument lies. |
| **LusidInstrumentId** | **string** | Required | The unique Lusid Instrument Id (LUID) of the instrument that economics are for. |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The sub-holding properties which identify the Economic. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio. |
| **Buckets** | [List&lt;Bucket&gt;](Bucket.md) | Optional | Set of economic data related with each of the side impact of the transaction. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Economics(
    instrumentScope: "...",  // optional — The scope in which the instrument lies.
    lusidInstrumentId: "...",  // required — The unique Lusid Instrument Id (LUID) of the instrument that economics are for.
    subHoldingKeys: new PerpetualProperty(...),  // optional — The sub-holding properties which identify the Economic. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio.
    buckets: new List<Bucket>()  // optional — Set of economic data related with each of the side impact of the transaction.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Economics>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [Bucket](Bucket.md) — used in `Buckets`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

