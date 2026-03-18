# Finbourne.Sdk.Lusid.Model.ClosePeriodDiaryEntryRequest

A definition for the period you wish to close
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DiaryEntryCode** | **string** | Optional | Unique code assigned to a period. When left blank a code will be created by the system in the format &#39;yyyyMMDD&#39;. |
| **Name** | **string** | Optional | Identifiable Name assigned to the period. Where left blank, the system will generate a name in the format &#39;yyyyMMDD&#39;. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effective time of the diary entry. |
| **QueryAsAt** | **DateTimeOffset?** | Optional | The query time of the diary entry. Defaults to latest. |
| **Status** | **string** | Optional | The status of a Diary Entry of Type &#39;PeriodBoundary&#39;. Defaults to &#39;Estimate&#39; when closing a period, and supports &#39;Estimate&#39; and &#39;Final&#39; for closing periods and &#39;Final&#39; for locking periods. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the diary entry. |
| **ClosingOptions** | **List&lt;string&gt;** | Optional | The options which will be executed once a period is closed or locked. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ClosePeriodDiaryEntryRequest(
    diaryEntryCode: "...",  // optional — Unique code assigned to a period. When left blank a code will be created by the system in the format &#39;yyyyMMDD&#39;.
    name: "...",  // optional — Identifiable Name assigned to the period. Where left blank, the system will generate a name in the format &#39;yyyyMMDD&#39;.
    effectiveAt: DateTimeOffset.Now,  // optional — The effective time of the diary entry.
    queryAsAt: DateTimeOffset.Now,  // optional — The query time of the diary entry. Defaults to latest.
    status: "...",  // optional — The status of a Diary Entry of Type &#39;PeriodBoundary&#39;. Defaults to &#39;Estimate&#39; when closing a period, and supports &#39;Estimate&#39; and &#39;Final&#39; for closing periods and &#39;Final&#39; for locking periods.
    properties: new Property(...),  // optional — A set of properties for the diary entry.
    closingOptions:   // optional — The options which will be executed once a period is closed or locked.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ClosePeriodDiaryEntryRequest>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

