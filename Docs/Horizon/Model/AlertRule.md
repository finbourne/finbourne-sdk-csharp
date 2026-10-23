# Finbourne.Sdk.Horizon.Model.AlertRule

An alert rule on an integration instance. Finbourne.Horizon.Integrations.Web.Dto.AlertRule.Type selects the rule and decides which of the optional fields apply. A field that does not belong to the selected type is rejected.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The rule type (Allowed: MustStartBy, MaxDuration, FailedAfterRetries) |
| **Severity** | **string** | Optional | The severity alerts from this rule are raised at (Allowed: Critical, High, Medium, Low, Informational). Critical pages on-call for a client-facing outage. High needs action today. Medium is a missed or late run. Low is an overrun or record-count check. Informational never pages. Defaults per type when omitted: MustStartBy and FailedAfterRetries Medium, MaxDuration Low. |
| **TimeOfDay** | **string** | Optional | MustStartBy only. The local time of day, as HH:mm, by which a run must have started. |
| **VarTimeZone** | **string** | Optional | MustStartBy only. The IANA or Windows time zone id that TimeOfDay is expressed in. |
| **DaysOfWeek** | **List&lt;string&gt;** | Optional | MustStartBy only. The days the rule applies on, by name (e.g. Monday). Every day when omitted. |
| **GraceMinutes** | **int?** | Optional | MustStartBy only. Minutes after TimeOfDay before a missing run counts as a breach. 0 when omitted. |
| **MaxMinutes** | **int?** | Optional | MaxDuration only. Alert once a run has been running for longer than this many minutes. Minimum 10. |
| **IncludePaused** | **bool?** | Optional | MaxDuration only. Also measure paused runs. False when omitted. |
| **AlertOnFirstFailure** | **bool?** | Optional | FailedAfterRetries only. Also alert on the first failure of a retry chain, not only when the retries are exhausted. False when omitted. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new AlertRule(
    type: "...",  // required — The rule type (Allowed: MustStartBy, MaxDuration, FailedAfterRetries)
    severity: "...",  // optional — The severity alerts from this rule are raised at (Allowed: Critical, High, Medium, Low, Informational). Critical pages on-call for a client-facing outage. High needs action today. Medium is a missed or late run. Low is an overrun or record-count check. Informational never pages. Defaults per type when omitted: MustStartBy and FailedAfterRetries Medium, MaxDuration Low.
    timeOfDay: "...",  // optional — MustStartBy only. The local time of day, as HH:mm, by which a run must have started.
    varTimeZone: "...",  // optional — MustStartBy only. The IANA or Windows time zone id that TimeOfDay is expressed in.
    daysOfWeek: ,  // optional — MustStartBy only. The days the rule applies on, by name (e.g. Monday). Every day when omitted.
    graceMinutes: 0,  // optional — MustStartBy only. Minutes after TimeOfDay before a missing run counts as a breach. 0 when omitted.
    maxMinutes: 0,  // optional — MaxDuration only. Alert once a run has been running for longer than this many minutes. Minimum 10.
    includePaused: true,  // optional — MaxDuration only. Also measure paused runs. False when omitted.
    alertOnFirstFailure: true  // optional — FailedAfterRetries only. Also alert on the first failure of a retry chain, not only when the retries are exhausted. False when omitted.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AlertRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

