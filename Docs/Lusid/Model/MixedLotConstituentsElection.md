# Finbourne.Sdk.Lusid.Model.MixedLotConstituentsElection

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ElectionKey** | **string** | Required | *No description available.* |
| **IsDefault** | **bool** | Optional | *No description available.* |
| **IsChosen** | **bool** | Optional | *No description available.* |
| **SecuritiesConstituents** | [List&lt;SecurityOfferConstituent&gt;](SecurityOfferConstituent.md) | Optional | *No description available.* |
| **CashConstituents** | [List&lt;CashOfferConstituent&gt;](CashOfferConstituent.md) | Optional | *No description available.* |
| **CostFactor** | **decimal?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MixedLotConstituentsElection(
    electionKey: "...",  // required
    isDefault: true,  // optional
    isChosen: true,  // optional
    securitiesConstituents: new List<SecurityOfferConstituent>(),  // optional
    cashConstituents: new List<CashOfferConstituent>(),  // optional
    costFactor: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MixedLotConstituentsElection>(json);
```

- [SecurityOfferConstituent](SecurityOfferConstituent.md)
- [CashOfferConstituent](CashOfferConstituent.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

