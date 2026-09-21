# Finbourne.Sdk.Lusid.Model.RecDatesReconciled

The left and right effective and asAt dates of the data reconciled in a run, plus the exclusive lower bound of each side's activity window on activity-based rec types.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LeftEffectiveAt** | **DateTimeOffset** | Required | The effective datetime of the data reconciled on the left side. |
| **LeftAsAt** | **DateTimeOffset** | Required | The asAt datetime of the data reconciled on the left side. |
| **RightEffectiveAt** | **DateTimeOffset** | Required | The effective datetime of the data reconciled on the right side. |
| **RightAsAt** | **DateTimeOffset** | Required | The asAt datetime of the data reconciled on the right side. |
| **LeftActivitySinceEffectiveAt** | **DateTimeOffset?** | Optional | The exclusive lower bound of the left side&#39;s activity window, so the window is (leftActivitySinceEffectiveAt, leftEffectiveAt]. Populated only on activity-based rec types; null on point-in-time rec types and when the definition has no activity window. |
| **RightActivitySinceEffectiveAt** | **DateTimeOffset?** | Optional | The exclusive lower bound of the right side&#39;s activity window, so the window is (rightActivitySinceEffectiveAt, rightEffectiveAt]. Populated only on activity-based rec types; null on point-in-time rec types and when the definition has no activity window. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDatesReconciled(
    leftEffectiveAt: DateTimeOffset.Now,  // required — The effective datetime of the data reconciled on the left side.
    leftAsAt: DateTimeOffset.Now,  // required — The asAt datetime of the data reconciled on the left side.
    rightEffectiveAt: DateTimeOffset.Now,  // required — The effective datetime of the data reconciled on the right side.
    rightAsAt: DateTimeOffset.Now,  // required — The asAt datetime of the data reconciled on the right side.
    leftActivitySinceEffectiveAt: DateTimeOffset.Now,  // optional — The exclusive lower bound of the left side&#39;s activity window, so the window is (leftActivitySinceEffectiveAt, leftEffectiveAt]. Populated only on activity-based rec types; null on point-in-time rec types and when the definition has no activity window.
    rightActivitySinceEffectiveAt: DateTimeOffset.Now  // optional — The exclusive lower bound of the right side&#39;s activity window, so the window is (rightActivitySinceEffectiveAt, rightEffectiveAt]. Populated only on activity-based rec types; null on point-in-time rec types and when the definition has no activity window.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecDatesReconciled>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

