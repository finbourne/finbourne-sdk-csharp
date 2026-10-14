# Finbourne.Sdk.Lusid.Model.AllocationEventUseOfProceeds

One row of a CapitalCall Allocation Event's use of proceeds: what part of the call pays for what.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Purpose** | **string** | Required | What the row pays for: Investment, FacilityRepayment, FacilityInterest, ManagementFee or Expenses. Available values: Investment, FacilityRepayment, FacilityInterest, ManagementFee, Expenses. |
| **DealId** | **string** | Optional | The deal the row funds, or whose facility draw it repays. Required for an Investment row. |
| **Amount** | **decimal** | Required | The part of the call the row takes, in the event currency. Greater than zero. |
| **FacilityId** | **string** | Optional | The facility the row repays. Required for a FacilityRepayment row; on an Investment row it is filled in from the deal&#39;s funding when the call is computed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventUseOfProceeds(
    purpose: "...",  // required — What the row pays for: Investment, FacilityRepayment, FacilityInterest, ManagementFee or Expenses. Available values: Investment, FacilityRepayment, FacilityInterest, ManagementFee, Expenses.
    dealId: "...",  // optional — The deal the row funds, or whose facility draw it repays. Required for an Investment row.
    amount: 0.0d,  // required — The part of the call the row takes, in the event currency. Greater than zero.
    facilityId: "..."  // optional — The facility the row repays. Required for a FacilityRepayment row; on an Investment row it is filled in from the deal&#39;s funding when the call is computed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventUseOfProceeds>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

