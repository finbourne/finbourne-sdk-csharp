# Finbourne.Sdk.Lusid.Model.RecDatasetSchema

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The kind of dataset this side draws on. One of: PortfolioContents, LusidEntity, RelationalData. At most one side may be RelationalData. Available values: PortfolioContents, LusidEntity, RelationalData. |
| **EntityType** | **string** | Optional | The entity within the dataset. Required when type is PortfolioContents, in which case it is one of: Holding, Valuation, Transaction, OutputTransaction, SettlementActivity. Must be omitted when type is RelationalData. Available values: Holding, Valuation, Transaction, OutputTransaction, SettlementActivity. |
| **RelationalDatasetDefinitionId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDatasetSchema(
    type: "...",  // required — The kind of dataset this side draws on. One of: PortfolioContents, LusidEntity, RelationalData. At most one side may be RelationalData. Available values: PortfolioContents, LusidEntity, RelationalData.
    entityType: "...",  // optional — The entity within the dataset. Required when type is PortfolioContents, in which case it is one of: Holding, Valuation, Transaction, OutputTransaction, SettlementActivity. Must be omitted when type is RelationalData. Available values: Holding, Valuation, Transaction, OutputTransaction, SettlementActivity.
    relationalDatasetDefinitionId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecDatasetSchema>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

