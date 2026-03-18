# Finbourne.Sdk.Lusid.Model.InvestorIdentifier

Identification of an Investor on the LUSID API.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorType** | **string** | Required | The type of the investor of the Investor Record. Can be either a Person, LegalEntity or Nominee. |
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Optional | Single identifier that should target the desired person or legal entity |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InvestorIdentifier(
    investorType: "...",  // required — The type of the investor of the Investor Record. Can be either a Person, LegalEntity or Nominee.
    identifiers:   // optional — Single identifier that should target the desired person or legal entity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InvestorIdentifier>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

