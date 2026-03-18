# Finbourne.Sdk.Horizon.Model.PermIdData

PermId Data Structure
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Figi** | **string** | Required | FIGI assigned to the instrument. |
| **Ticker** | **string** | Required | Ticker assigned to the instrument |
| **Mic** | **string** | Required | ISO market identification code(MIC) of the desired instrument(s) |
| **QuotePermId** | **string** | Required | QuotePermId of the instrument |
| **IsPrimaryQuote** | **bool** | Required | If the quote is primary |
| **LegalEntityIdentifier** | **string** | Optional | LEI assigned to the instrument |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new PermIdData(
    figi: "...",  // required — FIGI assigned to the instrument.
    ticker: "...",  // required — Ticker assigned to the instrument
    mic: "...",  // required — ISO market identification code(MIC) of the desired instrument(s)
    quotePermId: "...",  // required — QuotePermId of the instrument
    isPrimaryQuote: true,  // required — If the quote is primary
    legalEntityIdentifier: "..."  // optional — LEI assigned to the instrument
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PermIdData>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

