# Finbourne.Sdk.Lusid.Model.AllocationPostingFundLine

One transaction a booking writes on the fund's own books.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | The deterministic identifier of the posting: the booking reference, investor record, commitment line, component and side. |
| **Portfolio** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TransactionType** | **string** | Optional | The transaction type written on the fund side, for instance PA.ContributionCalled. |
| **Amount** | **decimal** | Optional | The amount posted, in the event currency. |
| **Component** | **string** | Optional | The component of the event the posting carries. |
| **InvestorRecordId** | **string** | Optional | The investor record the posting is for. |
| **ViaVehicle** | **string** | Optional | The vehicle the investor&#39;s share reached the fund through, when it did not come direct. |
| **AdmissionVehicle** | **string** | Optional | The vehicle the investor was admitted to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationPostingFundLine(
    id: "...",  // optional — The deterministic identifier of the posting: the booking reference, investor record, commitment line, component and side.
    portfolio: new ResourceId(...),  // optional
    transactionType: "...",  // optional — The transaction type written on the fund side, for instance PA.ContributionCalled.
    amount: 0.0d,  // optional — The amount posted, in the event currency.
    component: "...",  // optional — The component of the event the posting carries.
    investorRecordId: "...",  // optional — The investor record the posting is for.
    viaVehicle: "...",  // optional — The vehicle the investor&#39;s share reached the fund through, when it did not come direct.
    admissionVehicle: "..."  // optional — The vehicle the investor was admitted to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationPostingFundLine>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

