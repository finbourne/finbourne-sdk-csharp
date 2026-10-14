# Finbourne.Sdk.Lusid.Model.DealingFlowSummary

The transfer agency estimates a swing decision was made on: how many orders were dealt at the valuation point and what they summed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Count** | **int** | Required | How many orders were summed. |
| **GrossInflow** | **decimal** | Required | The sum of the inflows, in the fund currency. Zero or more. |
| **GrossOutflow** | **decimal** | Required | The sum of the outflows, in the fund currency, as a magnitude. Zero or more. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DealingFlowSummary(
    count: 0,  // required — How many orders were summed.
    grossInflow: 0.0d,  // required — The sum of the inflows, in the fund currency. Zero or more.
    grossOutflow: 0.0d  // required — The sum of the outflows, in the fund currency, as a magnitude. Zero or more.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DealingFlowSummary>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

