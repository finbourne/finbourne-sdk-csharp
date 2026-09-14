# Finbourne.Sdk.Lusid.Model.ConsentGrantedElection

Election to grant consent to the proposed action (CONY), optionally in return for a consent fee.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ElectionKey** | **string** | Required | Unique key associated to this election. |
| **IsDefault** | **bool** | Optional | Is this election automatically applied in the absence of an election having been made.  May only be true for one election if multiple are provided. |
| **IsChosen** | **bool** | Optional | Is this the election that has been explicitly chosen from multiple options. |
| **ConsentFeePrice** | **decimal?** | Optional | Optional. The consent fee paid per unit for granting consent. |
| **ConsentFeeCurrency** | **string** | Optional | Optional. Currency of the consent fee. Required if a consent fee price is provided. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ConsentGrantedElection(
    electionKey: "...",  // required — Unique key associated to this election.
    isDefault: true,  // optional — Is this election automatically applied in the absence of an election having been made.  May only be true for one election if multiple are provided.
    isChosen: true,  // optional — Is this the election that has been explicitly chosen from multiple options.
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
var instance = JsonConvert.DeserializeObject<ConsentGrantedElection>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

