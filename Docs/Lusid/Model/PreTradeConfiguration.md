# Finbourne.Sdk.Lusid.Model.PreTradeConfiguration

Specification object for the pre trade configuration parameters of a compliance run
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IncludeEntityTypes** | **string** | Required | Controls whether Orders and Allocations orders are included in the Portfolio valuation done for this compliance run.  Valid values are:  None (to account for Transactions only), Allocations (to include Allocations and Transactions) and  OrdersAndAllocations (to include Orders, Allocations and Transactions). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PreTradeConfiguration(
    includeEntityTypes: "..."  // required — Controls whether Orders and Allocations orders are included in the Portfolio valuation done for this compliance run.  Valid values are:  None (to account for Transactions only), Allocations (to include Allocations and Transactions) and  OrdersAndAllocations (to include Orders, Allocations and Transactions).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PreTradeConfiguration>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

