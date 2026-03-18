# Finbourne.Sdk.Lusid.Model.InstrumentResolutionDetail

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | Unique instrument identifiers |
| **LusidInstrumentId** | **string** | Optional | LUSID&#39;s internal unique instrument identifier, resolved from the instrument identifiers *(read-only)* |
| **InstrumentScope** | **string** | Optional | The scope in which the instrument lies. *(read-only)* |
| **LaunchPrice** | **decimal?** | Optional | The launch price set when a shareclass is added to the fund. Defaults to 1. |
| **LaunchDate** | **DateTimeOffset?** | Optional | The launch date set when a shareclass is added to the fund. Defaults to Fund Inception Date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentResolutionDetail(
    instrumentIdentifiers: ,  // required — Unique instrument identifiers
    lusidInstrumentId: "...",  // optional — LUSID&#39;s internal unique instrument identifier, resolved from the instrument identifiers
    instrumentScope: "...",  // optional — The scope in which the instrument lies.
    launchPrice: 0.0d,  // optional — The launch price set when a shareclass is added to the fund. Defaults to 1.
    launchDate: DateTimeOffset.Now  // optional — The launch date set when a shareclass is added to the fund. Defaults to Fund Inception Date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentResolutionDetail>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

