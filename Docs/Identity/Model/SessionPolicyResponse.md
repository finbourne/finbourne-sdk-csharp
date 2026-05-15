# Finbourne.Sdk.Identity.Model.SessionPolicyResponse

Session timing settings.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MaxSessionIdleMinutes** | **long?** | Optional | Maximum minutes a user&#39;s session can be idle before re-authentication is required. |
| **MaxSessionLifetimeMinutes** | **long?** | Optional | Maximum minutes a user&#39;s session can live in total. When absent, sessions do not expire. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new SessionPolicyResponse(
    maxSessionIdleMinutes: 0L,  // optional — Maximum minutes a user&#39;s session can be idle before re-authentication is required.
    maxSessionLifetimeMinutes: 0L  // optional — Maximum minutes a user&#39;s session can live in total. When absent, sessions do not expire.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SessionPolicyResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

