# Finbourne.Sdk.Identity.Model.SystemLog

A system log event
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Actor** | [LogActor](LogActor.md) | Optional | *No description available.* |
| **AuthenticationContext** | [LogAuthenticationContext](LogAuthenticationContext.md) | Optional | *No description available.* |
| **ClientInfo** | [LogClientInfo](LogClientInfo.md) | Optional | *No description available.* |
| **DebugContext** | [LogDebugContext](LogDebugContext.md) | Optional | *No description available.* |
| **DisplayMessage** | **string** | Optional | Represents a DisplayMessage resource in the Okta API |
| **EventType** | **string** | Optional | Represents a EventType resource in the Okta API |
| **LegacyEventType** | **string** | Optional | Represents a LegacyEventType resource in the Okta API |
| **Outcome** | [LogOutcome](LogOutcome.md) | Optional | *No description available.* |
| **Published** | **DateTimeOffset?** | Optional | Represents when Published in the Okta API |
| **Request** | [LogRequest](LogRequest.md) | Optional | *No description available.* |
| **SecurityContext** | [LogSecurityContext](LogSecurityContext.md) | Optional | *No description available.* |
| **Severity** | [LogSeverity](LogSeverity.md) | Optional | *No description available.* |
| **Target** | [List&lt;LogTarget&gt;](LogTarget.md) | Optional | Represents a LogTarget resource in the Okta API |
| **Transaction** | [LogTransaction](LogTransaction.md) | Optional | *No description available.* |
| **Uuid** | **string** | Optional | Represents Uuid in the Okta API |
| **VarVersion** | **string** | Optional | Represents a Version in the Okta API |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new SystemLog(
    actor: new LogActor(...),  // optional
    authenticationContext: new LogAuthenticationContext(...),  // optional
    clientInfo: new LogClientInfo(...),  // optional
    debugContext: new LogDebugContext(...),  // optional
    displayMessage: "...",  // optional — Represents a DisplayMessage resource in the Okta API
    eventType: "...",  // optional — Represents a EventType resource in the Okta API
    legacyEventType: "...",  // optional — Represents a LegacyEventType resource in the Okta API
    outcome: new LogOutcome(...),  // optional
    published: DateTimeOffset.Now,  // optional — Represents when Published in the Okta API
    request: new LogRequest(...),  // optional
    securityContext: new LogSecurityContext(...),  // optional
    severity: new LogSeverity(...),  // optional
    target: new List<LogTarget>(),  // optional — Represents a LogTarget resource in the Okta API
    transaction: new LogTransaction(...),  // optional
    uuid: "...",  // optional — Represents Uuid in the Okta API
    varVersion: "..."  // optional — Represents a Version in the Okta API
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SystemLog>(json);
```


## Related Models

- [LogActor](LogActor.md)
- [LogAuthenticationContext](LogAuthenticationContext.md)
- [LogClientInfo](LogClientInfo.md)
- [LogDebugContext](LogDebugContext.md)
- [LogOutcome](LogOutcome.md)
- [LogRequest](LogRequest.md)
- [LogSecurityContext](LogSecurityContext.md)
- [LogSeverity](LogSeverity.md)
- [LogTarget](LogTarget.md) — used in `Target`
- [LogTransaction](LogTransaction.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

