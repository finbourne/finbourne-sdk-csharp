# Finbourne.Sdk.Lusid.Model.GetReferencePortfolioConstituentsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveFrom** | **DateTimeOffset** | Required | *No description available.* |
| **WeightType** | **string** | Required | The available values are: Static, Floating, Periodical |
| **PeriodType** | **string** | Optional | The available values are: Daily, Weekly, Monthly, Quarterly, Annually |
| **PeriodCount** | **int?** | Optional | *No description available.* |
| **Constituents** | [List&lt;ReferencePortfolioConstituent&gt;](ReferencePortfolioConstituent.md) | Required | Set of constituents (instrument/weight pairings) |
| **Href** | **string** | Optional | The Uri that returns the same result as the original request,  but may include resolved as at time(s). |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GetReferencePortfolioConstituentsResponse(
    effectiveFrom: DateTimeOffset.Now,  // required
    weightType: "...",  // required — The available values are: Static, Floating, Periodical
    periodType: "...",  // optional — The available values are: Daily, Weekly, Monthly, Quarterly, Annually
    periodCount: 0,  // optional
    constituents: new List<ReferencePortfolioConstituent>(),  // required — Set of constituents (instrument/weight pairings)
    href: "...",  // optional — The Uri that returns the same result as the original request,  but may include resolved as at time(s).
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GetReferencePortfolioConstituentsResponse>(json);
```

- [ReferencePortfolioConstituent](ReferencePortfolioConstituent.md) — used in `Constituents`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

