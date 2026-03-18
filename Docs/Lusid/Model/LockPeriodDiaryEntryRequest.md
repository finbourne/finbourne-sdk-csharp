# Finbourne.Sdk.Lusid.Model.LockPeriodDiaryEntryRequest

A definition for the period you wish to lock
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DiaryEntryCode** | **string** | Optional | Unique code assigned to a period. When left blank last closed period will be located. |
| **ClosingOptions** | **List&lt;string&gt;** | Optional | The options which will be executed once a period is closed or locked. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LockPeriodDiaryEntryRequest(
    diaryEntryCode: "...",  // optional — Unique code assigned to a period. When left blank last closed period will be located.
    closingOptions:   // optional — The options which will be executed once a period is closed or locked.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LockPeriodDiaryEntryRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

