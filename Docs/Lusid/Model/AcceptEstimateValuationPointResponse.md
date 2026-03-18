# Finbourne.Sdk.Lusid.Model.AcceptEstimateValuationPointResponse

The Valuation Point Data Response for AcceptEstimate called on the Fund and specified date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **CandidateValuationPoint** | [ValuationPointDataResponse](ValuationPointDataResponse.md) | Required | *No description available.* |
| **LatestValuationPoint** | [ValuationPointDataResponse](ValuationPointDataResponse.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AcceptEstimateValuationPointResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    candidateValuationPoint: new ValuationPointDataResponse(...),  // required
    latestValuationPoint: new ValuationPointDataResponse(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AcceptEstimateValuationPointResponse>(json);
```

- [ValuationPointDataResponse](ValuationPointDataResponse.md)
- [ValuationPointDataResponse](ValuationPointDataResponse.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

