# Finbourne.Sdk.Lusid.Model.HoldingContext

Holding context node.  Contains settings that control how LUSID handles holdings within portfolios.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaxLotLevelHoldings** | **bool** | Optional | Whether or not to expand the holdings to return the underlying tax-lots. Defaults to True. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new HoldingContext(
    taxLotLevelHoldings: true  // optional — Whether or not to expand the holdings to return the underlying tax-lots. Defaults to True.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HoldingContext>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

