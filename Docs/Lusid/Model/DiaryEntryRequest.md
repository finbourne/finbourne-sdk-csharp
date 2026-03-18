# Finbourne.Sdk.Lusid.Model.DiaryEntryRequest

The request to add a diary entry
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DiaryEntryCode** | **string** | Required | The code of the diary entry. |
| **Name** | **string** | Optional | The name of the diary entry. |
| **Status** | **string** | Optional | The status of a Diary Entry of Type &#39;Other&#39;. Defaults to &#39;Undefined&#39; and supports &#39;Undefined&#39;, &#39;Estimate&#39;, &#39;Candidate&#39;, and &#39;Final&#39;. |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective time of the diary entry. |
| **QueryAsAt** | **DateTimeOffset?** | Optional | The query time of the diary entry. Defaults to latest. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the diary entry. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DiaryEntryRequest(
    diaryEntryCode: "...",  // required — The code of the diary entry.
    name: "...",  // optional — The name of the diary entry.
    status: "...",  // optional — The status of a Diary Entry of Type &#39;Other&#39;. Defaults to &#39;Undefined&#39; and supports &#39;Undefined&#39;, &#39;Estimate&#39;, &#39;Candidate&#39;, and &#39;Final&#39;.
    effectiveAt: DateTimeOffset.Now,  // required — The effective time of the diary entry.
    queryAsAt: DateTimeOffset.Now,  // optional — The query time of the diary entry. Defaults to latest.
    properties: new Property(...)  // optional — A set of properties for the diary entry.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DiaryEntryRequest>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

