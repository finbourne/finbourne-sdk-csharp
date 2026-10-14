# Finbourne.Sdk.Lusid.Model.AllocationMapBasisValue

The value one investor record is weighted by when an Allocation Map is resolved.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record the basis value belongs to. |
| **BasisValue** | **decimal** | Required | The value the investor record is weighted by, for example its commitment. |
| **Currency** | **string** | Optional | The currency the basis value is held in. Absent means the base currency of the map&#39;s member fund. When the basis values span more than one currency, each is translated into the fund&#39;s base currency at the spot rate on the event date, from the fund&#39;s ABOR recipe, before it weights the allocation. The rate on the event date is the latest quote at or before 00:00 UTC on that date. |
| **CommitmentLineId** | **string** | Optional | For a Commitment event, the commitment line the amount is recorded against. The basis value is then the signed commitment amount itself: positive commits, negative releases. Not used for other event types. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapBasisValue(
    investorRecordId: "...",  // required — The investor record the basis value belongs to.
    basisValue: 0.0d,  // required — The value the investor record is weighted by, for example its commitment.
    currency: "...",  // optional — The currency the basis value is held in. Absent means the base currency of the map&#39;s member fund. When the basis values span more than one currency, each is translated into the fund&#39;s base currency at the spot rate on the event date, from the fund&#39;s ABOR recipe, before it weights the allocation. The rate on the event date is the latest quote at or before 00:00 UTC on that date.
    commitmentLineId: "...",  // optional — For a Commitment event, the commitment line the amount is recorded against. The basis value is then the signed commitment amount itself: positive commits, negative releases. Not used for other event types.
    portfolioId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapBasisValue>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

