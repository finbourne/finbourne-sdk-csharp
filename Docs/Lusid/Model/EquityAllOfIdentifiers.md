# Finbourne.Sdk.Lusid.Model.EquityAllOfIdentifiers

External market codes and identifiers for the equity, e.g. IBM
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LusidInstrumentId** | **string** | Optional | *No description available.* |
| **Isin** | **string** | Optional | *No description available.* |
| **Sedol** | **string** | Optional | *No description available.* |
| **Cusip** | **string** | Optional | *No description available.* |
| **ClientInternal** | **string** | Optional | *No description available.* |
| **Figi** | **string** | Optional | *No description available.* |
| **RIC** | **string** | Optional | *No description available.* |
| **QuotePermId** | **string** | Optional | *No description available.* |
| **REDCode** | **string** | Optional | *No description available.* |
| **BBGId** | **string** | Optional | *No description available.* |
| **ICECode** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EquityAllOfIdentifiers(
    lusidInstrumentId: "...",  // optional
    isin: "...",  // optional
    sedol: "...",  // optional
    cusip: "...",  // optional
    clientInternal: "...",  // optional
    figi: "...",  // optional
    rIC: "...",  // optional
    quotePermId: "...",  // optional
    rEDCode: "...",  // optional
    bBGId: "...",  // optional
    iCECode: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EquityAllOfIdentifiers>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

