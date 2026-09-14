# Finbourne.Sdk.Lusid.Model.ConsentAndTenderElection

Election to both grant consent and tender the holding (CTEN), optionally for a tender offer price and consent fee.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ElectionKey** | **string** | Required | Unique key associated to this election. |
| **IsDefault** | **bool** | Optional | Is this election automatically applied in the absence of an election having been made.  May only be true for one election if multiple are provided. |
| **IsChosen** | **bool** | Optional | Is this the election that has been explicitly chosen from multiple options. |
| **TenderOfferPrice** | **decimal?** | Optional | Optional. Price per unit offered for the tendered holding. |
| **TenderOfferCurrency** | **string** | Optional | Optional. Currency of the tender offer. Required if a tender offer price is provided. |
| **ConsentFeePrice** | **decimal?** | Optional | Optional. The consent fee paid per unit for granting consent. |
| **ConsentFeeCurrency** | **string** | Optional | Optional. Currency of the consent fee. Required if a consent fee price is provided. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ConsentAndTenderElection(
    electionKey: "...",  // required — Unique key associated to this election.
    isDefault: true,  // optional — Is this election automatically applied in the absence of an election having been made.  May only be true for one election if multiple are provided.
    isChosen: true,  // optional — Is this the election that has been explicitly chosen from multiple options.
    tenderOfferPrice: 0.0d,  // optional — Optional. Price per unit offered for the tendered holding.
    tenderOfferCurrency: "...",  // optional — Optional. Currency of the tender offer. Required if a tender offer price is provided.
    consentFeePrice: 0.0d,  // optional — Optional. The consent fee paid per unit for granting consent.
    consentFeeCurrency: "..."  // optional — Optional. Currency of the consent fee. Required if a consent fee price is provided.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ConsentAndTenderElection>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

