# Finbourne.Sdk.Lusid.Model.CreatePortfolioDetails

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CorporateActionSourceId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TaxLotSelectionCostBasis** | **string** | Optional | The cost figure that cost-referencing accounting methods evaluate when selecting tax lots for a disposal. This can be: Cost or AmortisedCost. If not supplied, the portfolio&#39;s current value is left unchanged; supply Default to reset it. A reset or never-configured basis reads back as absent. Available values: Default, Cost, AmortisedCost. |
| **FractionalUnitsTrueUpConfiguration** | [FractionalUnitsTrueUpConfiguration](FractionalUnitsTrueUpConfiguration.md) | Optional | *No description available.* |
| **HoldingsFungibility** | **string** | Optional | Whether the portfolio&#39;s holdings are fungible across the currencies of a currency group. This can be: Default or Enabled. If not supplied, the portfolio&#39;s current value is left unchanged; supply Default to reset it. A reset or never-configured flag reads back as absent. Available values: Default, Enabled. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreatePortfolioDetails(
    corporateActionSourceId: new ResourceId(...),  // optional
    taxLotSelectionCostBasis: "...",  // optional — The cost figure that cost-referencing accounting methods evaluate when selecting tax lots for a disposal. This can be: Cost or AmortisedCost. If not supplied, the portfolio&#39;s current value is left unchanged; supply Default to reset it. A reset or never-configured basis reads back as absent. Available values: Default, Cost, AmortisedCost.
    fractionalUnitsTrueUpConfiguration: new FractionalUnitsTrueUpConfiguration(...),  // optional
    holdingsFungibility: "..."  // optional — Whether the portfolio&#39;s holdings are fungible across the currencies of a currency group. This can be: Default or Enabled. If not supplied, the portfolio&#39;s current value is left unchanged; supply Default to reset it. A reset or never-configured flag reads back as absent. Available values: Default, Enabled.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreatePortfolioDetails>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [FractionalUnitsTrueUpConfiguration](FractionalUnitsTrueUpConfiguration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

