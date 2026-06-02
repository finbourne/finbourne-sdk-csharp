# Finbourne.Sdk.Lusid.Model.CashOfferConstituent

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OfferPrice** | **decimal** | Required | *No description available.* |
| **Currency** | **string** | Required | *No description available.* |
| **SettlementDate** | **DateTimeOffset** | Required | *No description available.* |
| **MinPieceSize** | **decimal?** | Optional | *No description available.* |
| **MinIncrement** | **decimal?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CashOfferConstituent(
    offerPrice: 0.0d,  // required
    currency: "...",  // required
    settlementDate: DateTimeOffset.Now,  // required
    minPieceSize: 0.0d,  // optional
    minIncrement: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CashOfferConstituent>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

