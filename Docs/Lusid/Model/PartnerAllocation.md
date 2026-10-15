# Finbourne.Sdk.Lusid.Model.PartnerAllocation

One partner's share of an allocation pool.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record the allocation belongs to. |
| **BasisWeight** | **decimal** | Required | The partner&#39;s weight in the pool&#39;s basis. |
| **Amount** | **decimal** | Required | The amount allocated to the partner. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerAllocation(
    investorRecordId: "...",  // required — The investor record the allocation belongs to.
    basisWeight: 0.0d,  // required — The partner&#39;s weight in the pool&#39;s basis.
    amount: 0.0d  // required — The amount allocated to the partner.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerAllocation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

