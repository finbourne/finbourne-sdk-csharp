# Finbourne.Sdk.Lusid.Model.DiaryEntry

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **AborId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **DiaryEntryCode** | **string** | Optional | The code of the diary entry. |
| **Type** | **string** | Required | The type of the diary entry. |
| **Name** | **string** | Optional | The name of the diary entry. |
| **Status** | **string** | Required | The status of the diary entry. Statuses are constrained and defaulted by &#39;Type&#39; specified.   Type &#39;Other&#39; defaults to &#39;Undefined&#39; and supports &#39;Undefined&#39;, &#39;Estimate&#39;, &#39;Candidate&#39;, and &#39;Final&#39;.  Type &#39;PeriodBoundary&#39; defaults to &#39;Estimate&#39; when closing a period, and supports &#39;Estimate&#39; and &#39;Final&#39; for closing periods and &#39;Final&#39; for locking periods.  Type &#39;ValuationPoint&#39; defaults to &#39;Estimate&#39; when upserting a diary entry, moves to &#39;Candidate&#39; or &#39;Final&#39; when a ValuationPoint is accepted, and &#39;Final&#39; when it is finalised. |
| **ApplyClearDown** | **bool** | Optional | Defaults to false. Set to true if you want that the closed period to have the clear down applied. |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective time of the diary entry. |
| **QueryAsAt** | **DateTimeOffset** | Optional | The query time of the diary entry. Defaults to latest. |
| **PreviousEntryTime** | **DateTimeOffset** | Optional | The entry time of the previous diary entry. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the diary entry. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DiaryEntry(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    aborId: new ResourceId(...),  // optional
    diaryEntryCode: "...",  // optional — The code of the diary entry.
    type: "...",  // required — The type of the diary entry.
    name: "...",  // optional — The name of the diary entry.
    status: "...",  // required — The status of the diary entry. Statuses are constrained and defaulted by &#39;Type&#39; specified.   Type &#39;Other&#39; defaults to &#39;Undefined&#39; and supports &#39;Undefined&#39;, &#39;Estimate&#39;, &#39;Candidate&#39;, and &#39;Final&#39;.  Type &#39;PeriodBoundary&#39; defaults to &#39;Estimate&#39; when closing a period, and supports &#39;Estimate&#39; and &#39;Final&#39; for closing periods and &#39;Final&#39; for locking periods.  Type &#39;ValuationPoint&#39; defaults to &#39;Estimate&#39; when upserting a diary entry, moves to &#39;Candidate&#39; or &#39;Final&#39; when a ValuationPoint is accepted, and &#39;Final&#39; when it is finalised.
    applyClearDown: true,  // optional — Defaults to false. Set to true if you want that the closed period to have the clear down applied.
    effectiveAt: DateTimeOffset.Now,  // required — The effective time of the diary entry.
    queryAsAt: DateTimeOffset.Now,  // optional — The query time of the diary entry. Defaults to latest.
    previousEntryTime: DateTimeOffset.Now,  // optional — The entry time of the previous diary entry.
    properties: new Property(...),  // optional — A set of properties for the diary entry.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DiaryEntry>(json);
```

- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

