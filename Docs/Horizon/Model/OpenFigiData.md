# Finbourne.Sdk.Horizon.Model.OpenFigiData

OpenFIGI data structure
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Figi** | **string** | Required | FIGI assigned to the instrument. |
| **Name** | **string** | Optional | Various attributes of the instrument |
| **Ticker** | **string** | Optional | Various attributes of the instrument |
| **ExchangeCode** | **string** | Optional | Exchange code of the desired instrument(s) |
| **Mic** | **string** | Optional | ISO market identification code(MIC) of the desired instrument(s) |
| **ExchangeName** | **string** | Optional | Exchange name of the desired instrument(s) |
| **MarketSector** | **string** | Optional | Market sector description of the desired instrument(s) |
| **GeneralSecurityType** | **string** | Optional | Enum-like attributes of the instrument |
| **SecurityType** | **string** | Optional | Enum-like attributes of the instrument |
| **SecurityDescription** | **string** | Optional | Various attributes of the instrument |
| **CompositeFigi** | **string** | Optional | Various attributes of the instrument |
| **ShareClassFigi** | **string** | Optional | Various attributes of the instrument |
| **MatchType** | **string** | Optional | Type that the instrument matched against |
| **SearchInput** | **string** | Optional | Search input used to generate this response |
| **LusidInstrumentId** | **string** | Optional | If an instrument with this FIGI exists, the LUID of that instrument in LUSID |
| **LusidInstrumentScope** | **string** | Optional | If an instrument with this FIGI exists, the Scope of that instrument in LUSID |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new OpenFigiData(
    figi: "...",  // required — FIGI assigned to the instrument.
    name: "...",  // optional — Various attributes of the instrument
    ticker: "...",  // optional — Various attributes of the instrument
    exchangeCode: "...",  // optional — Exchange code of the desired instrument(s)
    mic: "...",  // optional — ISO market identification code(MIC) of the desired instrument(s)
    exchangeName: "...",  // optional — Exchange name of the desired instrument(s)
    marketSector: "...",  // optional — Market sector description of the desired instrument(s)
    generalSecurityType: "...",  // optional — Enum-like attributes of the instrument
    securityType: "...",  // optional — Enum-like attributes of the instrument
    securityDescription: "...",  // optional — Various attributes of the instrument
    compositeFigi: "...",  // optional — Various attributes of the instrument
    shareClassFigi: "...",  // optional — Various attributes of the instrument
    matchType: "...",  // optional — Type that the instrument matched against
    searchInput: "...",  // optional — Search input used to generate this response
    lusidInstrumentId: "...",  // optional — If an instrument with this FIGI exists, the LUID of that instrument in LUSID
    lusidInstrumentScope: "..."  // optional — If an instrument with this FIGI exists, the Scope of that instrument in LUSID
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OpenFigiData>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

