# Finbourne.Sdk.Lusid.Model.PeriodDiaryEntriesReopenedResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **EffectiveFrom** | **DateTimeOffset?** | Optional | The effective datetime at which the deletion became valid. May be null in the case where multiple date times are applicable. |
| **AsAt** | **DateTimeOffset** | Required | The asAt datetime at which the deletion was committed to LUSID. |
| **PeriodDiaryEntriesRemoved** | **int** | Required | Number of Diary Entries removed as a result of reopening periods |
| **PeriodDiaryEntriesFrom** | **DateTimeOffset** | Required | The start point where periods were removed from |
| **PeriodDiaryEntriesTo** | **DateTimeOffset** | Required | The end point where periods were removed to |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PeriodDiaryEntriesReopenedResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    effectiveFrom: DateTimeOffset.Now,  // optional — The effective datetime at which the deletion became valid. May be null in the case where multiple date times are applicable.
    asAt: DateTimeOffset.Now,  // required — The asAt datetime at which the deletion was committed to LUSID.
    periodDiaryEntriesRemoved: 0,  // required — Number of Diary Entries removed as a result of reopening periods
    periodDiaryEntriesFrom: DateTimeOffset.Now,  // required — The start point where periods were removed from
    periodDiaryEntriesTo: DateTimeOffset.Now,  // required — The end point where periods were removed to
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PeriodDiaryEntriesReopenedResponse>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

