# Finbourne.Sdk.Lusid.Model.ShareClassDetails

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LusidInstrumentId** | **string** | Optional | LUSID&#39;s internal unique instrument identifier, resolved from the share class&#39; instrument identifiers |
| **InstrumentScope** | **string** | Optional | The scope in which the share class instrument lies. |
| **ShortCode** | **string** | Optional | The unique code within the fund for the share class instrument. |
| **DomCurrency** | **string** | Optional | The domestic currency of the share class instrument |
| **InstrumentActive** | **bool** | Optional | If the instrument of the share class is active. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ShareClassDetails(
    lusidInstrumentId: "...",  // optional — LUSID&#39;s internal unique instrument identifier, resolved from the share class&#39; instrument identifiers
    instrumentScope: "...",  // optional — The scope in which the share class instrument lies.
    shortCode: "...",  // optional — The unique code within the fund for the share class instrument.
    domCurrency: "...",  // optional — The domestic currency of the share class instrument
    instrumentActive: true  // optional — If the instrument of the share class is active.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ShareClassDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

