# Finbourne.Sdk.Lusid.Model.ReOpenPeriodDiaryEntryRequest

A definition for the period you wish to re open
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DiaryEntryCode** | **string** | Optional | Unique code assigned to a period. When left blank last period will be used. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReOpenPeriodDiaryEntryRequest(
    diaryEntryCode: "..."  // optional — Unique code assigned to a period. When left blank last period will be used.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReOpenPeriodDiaryEntryRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

