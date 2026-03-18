# Finbourne.Sdk.Lusid.Model.ClosedPeriod

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ClosedPeriodId** | **string** | Optional | The unique Id of the Closed Period. The ClosedPeriodId, together with the Timeline Scope and Code, uniquely identifies a Closed Period |
| **DisplayName** | **string** | Optional | The name of the Closed Period. |
| **Description** | **string** | Optional | A description for the Closed Period. |
| **EffectiveStart** | **DateTimeOffset** | Optional | The effective start of the Closed Period |
| **EffectiveEnd** | **DateTimeOffset** | Optional | The effective end of the Closed Period |
| **AsAtClosed** | **DateTimeOffset** | Optional | The asAt closed datetime for the Closed Period |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The Closed Periods properties. These will be from the &#39;ClosedPeriod&#39; domain. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **PostCloseActivities** | [List&lt;PostCloseActivity&gt;](PostCloseActivity.md) | Optional | All the post close activities for the closed period. |
| **HoldingsAsAtClosedOverride** | **DateTimeOffset?** | Optional | The optional AsAtClosed Override to use for building holdings in the Closed Period.If not specified, the AsAtClosed on the Closed Period will be used. |
| **ValuationAsAtClosedOverride** | **DateTimeOffset?** | Optional | The optional AsAtClosed Override to use for performing valuations in the Closed Period.If not specified, the AsAtClosed on the Closed Period will be used. |
| **BranchStatus** | **string** | Optional | The branch status of the closed period, e.g. Confirmed/Unconfirmed. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested asAt datetime. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ClosedPeriod(
    closedPeriodId: "...",  // optional — The unique Id of the Closed Period. The ClosedPeriodId, together with the Timeline Scope and Code, uniquely identifies a Closed Period
    displayName: "...",  // optional — The name of the Closed Period.
    description: "...",  // optional — A description for the Closed Period.
    effectiveStart: DateTimeOffset.Now,  // optional — The effective start of the Closed Period
    effectiveEnd: DateTimeOffset.Now,  // optional — The effective end of the Closed Period
    asAtClosed: DateTimeOffset.Now,  // optional — The asAt closed datetime for the Closed Period
    properties: new Property(...),  // optional — The Closed Periods properties. These will be from the &#39;ClosedPeriod&#39; domain.
    varVersion: new ModelVersion(...),  // optional
    postCloseActivities: new List<PostCloseActivity>(),  // optional — All the post close activities for the closed period.
    holdingsAsAtClosedOverride: DateTimeOffset.Now,  // optional — The optional AsAtClosed Override to use for building holdings in the Closed Period.If not specified, the AsAtClosed on the Closed Period will be used.
    valuationAsAtClosedOverride: DateTimeOffset.Now,  // optional — The optional AsAtClosed Override to use for performing valuations in the Closed Period.If not specified, the AsAtClosed on the Closed Period will be used.
    branchStatus: "...",  // optional — The branch status of the closed period, e.g. Confirmed/Unconfirmed.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested asAt datetime.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ClosedPeriod>(json);
```

- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [PostCloseActivity](PostCloseActivity.md) — used in `PostCloseActivities`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

