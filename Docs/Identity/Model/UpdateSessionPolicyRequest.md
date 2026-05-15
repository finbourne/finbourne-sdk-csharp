# Finbourne.Sdk.Identity.Model.UpdateSessionPolicyRequest

Session timing settings.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MaxSessionIdleMinutes** | **long** | Required | Maximum minutes a user&#39;s session can be idle before re-authentication is required. Must be between 5 minutes and 12 hours (720 minutes). |
| **MaxSessionLifetimeMinutes** | **long?** | Optional | Maximum minutes a user&#39;s session can live in total. Omit to disable session expiry; otherwise must be between 5 minutes and 24 hours (1440 minutes). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UpdateSessionPolicyRequest(
    maxSessionIdleMinutes: 0L,  // required — Maximum minutes a user&#39;s session can be idle before re-authentication is required. Must be between 5 minutes and 12 hours (720 minutes).
    maxSessionLifetimeMinutes: 0L  // optional — Maximum minutes a user&#39;s session can live in total. Omit to disable session expiry; otherwise must be between 5 minutes and 24 hours (1440 minutes).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateSessionPolicyRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

