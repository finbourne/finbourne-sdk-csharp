# Finbourne.Sdk.Lusid.Model.MarginItem

One margin arrangement under an agreement, either variation or initial.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The stable key that margin calls and custodian accounts refer to this item by. Unique across the agreement&#39;s variation and initial margin. |
| **TradeFilter** | **string** | Optional | A filter selecting the trades this item covers. Required where the agreement has more than one margin item. |
| **Settlement** | **string** | Optional | Whether margin is settled (Settled) or collateralised (Collateral). Optional. Available values: Collateral, Settled. |
| **LegalMechanism** | **string** | Optional | How title to posted collateral is held. One of TitleTransfer or SecurityInterest. Optional. Available values: TitleTransfer, SecurityInterest. |
| **WePost** | [PartyTerms](PartyTerms.md) | Required | *No description available.* |
| **TheyPost** | [PartyTerms](PartyTerms.md) | Required | *No description available.* |
| **EligibleCollateral** | [EligibleCollateralReferences](EligibleCollateralReferences.md) | Optional | *No description available.* |
| **Calculation** | [MarginCalculation](MarginCalculation.md) | Required | *No description available.* |
| **MarginAccounts** | [MarginAccounts](MarginAccounts.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginItem(
    code: "...",  // required — The stable key that margin calls and custodian accounts refer to this item by. Unique across the agreement&#39;s variation and initial margin.
    tradeFilter: "...",  // optional — A filter selecting the trades this item covers. Required where the agreement has more than one margin item.
    settlement: "...",  // optional — Whether margin is settled (Settled) or collateralised (Collateral). Optional. Available values: Collateral, Settled.
    legalMechanism: "...",  // optional — How title to posted collateral is held. One of TitleTransfer or SecurityInterest. Optional. Available values: TitleTransfer, SecurityInterest.
    wePost: new PartyTerms(...),  // required
    theyPost: new PartyTerms(...),  // required
    eligibleCollateral: new EligibleCollateralReferences(...),  // optional
    calculation: new MarginCalculation(...),  // required
    marginAccounts: new MarginAccounts(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginItem>(json);
```

- [PartyTerms](PartyTerms.md)
- [PartyTerms](PartyTerms.md)
- [EligibleCollateralReferences](EligibleCollateralReferences.md)
- [MarginCalculation](MarginCalculation.md)
- [MarginAccounts](MarginAccounts.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

