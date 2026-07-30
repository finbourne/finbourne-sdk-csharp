# Finbourne.Sdk.Lusid.Model.RecDatesReconciled

The left and right effective and asAt dates of the data reconciled in a run.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LeftEffectiveAt** | **DateTimeOffset** | Required | The effective datetime of the data reconciled on the left side. |
| **LeftAsAt** | **DateTimeOffset** | Required | The asAt datetime of the data reconciled on the left side. |
| **RightEffectiveAt** | **DateTimeOffset** | Required | The effective datetime of the data reconciled on the right side. |
| **RightAsAt** | **DateTimeOffset** | Required | The asAt datetime of the data reconciled on the right side. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDatesReconciled(
    leftEffectiveAt: DateTimeOffset.Now,  // required — The effective datetime of the data reconciled on the left side.
    leftAsAt: DateTimeOffset.Now,  // required — The asAt datetime of the data reconciled on the left side.
    rightEffectiveAt: DateTimeOffset.Now,  // required — The effective datetime of the data reconciled on the right side.
    rightAsAt: DateTimeOffset.Now  // required — The asAt datetime of the data reconciled on the right side.
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

