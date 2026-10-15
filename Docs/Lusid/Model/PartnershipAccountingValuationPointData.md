# Finbourne.Sdk.Lusid.Model.PartnershipAccountingValuationPointData

The partnership accounting view of a valuation point: what is left on the income summary to allocate to the  partners, and the configuration pack the allocation books under.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UnallocatedIncomeSummary** | **decimal** | Required | The balance on the income summary account over the valuation point&#39;s period that has not yet been allocated to the partners. Must be zero before the valuation point can be finalised. |
| **ConfigPackScope** | **string** | Required | The scope of the configuration pack. |
| **ConfigPackCode** | **string** | Required | The code of the configuration pack. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnershipAccountingValuationPointData(
    unallocatedIncomeSummary: 0.0d,  // required — The balance on the income summary account over the valuation point&#39;s period that has not yet been allocated to the partners. Must be zero before the valuation point can be finalised.
    configPackScope: "...",  // required — The scope of the configuration pack.
    configPackCode: "..."  // required — The code of the configuration pack.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnershipAccountingValuationPointData>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

