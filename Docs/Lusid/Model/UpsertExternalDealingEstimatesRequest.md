# Finbourne.Sdk.Lusid.Model.UpsertExternalDealingEstimatesRequest

One dealing point's dealing estimates for the fund named in the route, as a third-party transfer agent sends them.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DealingPoint** | **DateTimeOffset** | Required | *No description available.* |
| **Source** | [ExternalDealingEstimateSource](ExternalDealingEstimateSource.md) | Required | *No description available.* |
| **Complete** | **bool** | Optional | *No description available.* |
| **SentAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **Lines** | [Dictionary&lt;string, ExternalDealingEstimateLine&gt;](ExternalDealingEstimateLine.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertExternalDealingEstimatesRequest(
    dealingPoint: DateTimeOffset.Now,  // required
    source: new ExternalDealingEstimateSource(...),  // required
    complete: true,  // optional
    sentAt: DateTimeOffset.Now,  // optional
    lines: new ExternalDealingEstimateLine(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertExternalDealingEstimatesRequest>(json);
```

- [ExternalDealingEstimateSource](ExternalDealingEstimateSource.md)
- [ExternalDealingEstimateLine](ExternalDealingEstimateLine.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

