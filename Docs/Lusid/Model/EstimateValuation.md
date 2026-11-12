# Finbourne.Sdk.Lusid.Model.EstimateValuation

The swing decision read at both unit prices the transfer agency's unit-denominated orders could be valued at: this valuation point's estimate price and the last official price, with which one the decision used and how far apart they are.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DecisionPrice** | **string** | Required | The unit price the swing decision was taken on. &#39;EstimatePrice&#39; is the price struck at this valuation point; &#39;LastOfficialPrice&#39; is the unit price the previous valuation point published or, for a share class that has not published one yet, the launch price the class was set up with. |
| **AtEstimatePrice** | [DealingFlowValuation](DealingFlowValuation.md) | Required | *No description available.* |
| **AtLastOfficialPrice** | [DealingFlowValuation](DealingFlowValuation.md) | Optional | *No description available.* |
| **Difference** | [EstimateValuationDifference](EstimateValuationDifference.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EstimateValuation(
    decisionPrice: "...",  // required — The unit price the swing decision was taken on. &#39;EstimatePrice&#39; is the price struck at this valuation point; &#39;LastOfficialPrice&#39; is the unit price the previous valuation point published or, for a share class that has not published one yet, the launch price the class was set up with.
    atEstimatePrice: new DealingFlowValuation(...),  // required
    atLastOfficialPrice: new DealingFlowValuation(...),  // optional
    difference: new EstimateValuationDifference(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EstimateValuation>(json);
```

- [DealingFlowValuation](DealingFlowValuation.md)
- [DealingFlowValuation](DealingFlowValuation.md)
- [EstimateValuationDifference](EstimateValuationDifference.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

