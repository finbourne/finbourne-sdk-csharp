# Finbourne.Sdk.Lusid.Model.MarginSettlementLag

Business days between a margin call and settlement, by asset kind.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Cash** | **int** | Required | The business days between a cash margin call and settlement. |
| **Securities** | **int** | Required | The business days between a securities margin call and settlement. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginSettlementLag(
    cash: 0,  // required — The business days between a cash margin call and settlement.
    securities: 0  // required — The business days between a securities margin call and settlement.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginSettlementLag>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

