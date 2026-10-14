# Finbourne.Sdk.Lusid.Model.AllocationEventDealFunding

The details of a DealFunding Allocation Event: the deal the vehicle funds, where the money came from and which  investor records are excused from it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DealId** | **string** | Required | The deal the vehicle funds. A later capital call names it in an Investment row of its use of proceeds. |
| **FacilityId** | **string** | Optional | The subscription facility the funding was drawn from. Absent means the deal was paid from cash. |
| **ExcludedInvestorRecordIds** | **List&lt;string&gt;** | Optional | The investor records excused from the deal. They pay nothing towards it when it is called and the others take up their share. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventDealFunding(
    dealId: "...",  // required — The deal the vehicle funds. A later capital call names it in an Investment row of its use of proceeds.
    facilityId: "...",  // optional — The subscription facility the funding was drawn from. Absent means the deal was paid from cash.
    excludedInvestorRecordIds:   // optional — The investor records excused from the deal. They pay nothing towards it when it is called and the others take up their share.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventDealFunding>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

