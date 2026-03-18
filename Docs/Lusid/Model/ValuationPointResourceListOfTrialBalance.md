# Finbourne.Sdk.Lusid.Model.ValuationPointResourceListOfTrialBalance

ResourceList with extra header fields used by the various ValuationPoint endpoints for returning additional context related to the list of results.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartValuationPoint** | [DiaryEntry](DiaryEntry.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Values** | [List&lt;TrialBalance&gt;](TrialBalance.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **NextPage** | **string** | Optional | *No description available.* |
| **PreviousPage** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ValuationPointResourceListOfTrialBalance(
    startValuationPoint: new DiaryEntry(...),  // optional
    varVersion: new ModelVersion(...),  // required
    values: new List<TrialBalance>(),  // required
    href: "...",  // optional
    nextPage: "...",  // optional
    previousPage: "...",  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValuationPointResourceListOfTrialBalance>(json);
```


## Related Models

- [DiaryEntry](DiaryEntry.md)
- [ModelVersion](ModelVersion.md)
- [TrialBalance](TrialBalance.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

