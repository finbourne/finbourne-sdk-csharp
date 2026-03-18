# Finbourne.Sdk.Scheduler.Model.StartJobRequest

Job start definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Arguments** | **Dictionary&lt;string, string&gt;** | Optional | All arguments needed for the Job to run |
| **Notifications** | [List&lt;Notification&gt;](Notification.md) | Optional | Notifications for this Job |
| **UseAsAuth** | **string** | Optional | Id of user associated with schedule. All calls to FINBOURNE services as part of execution of this schedule will be authenticated as this  user. Can be null, in which case we&#39;ll default to that of the user  making this request |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new StartJobRequest(
    arguments: ,  // optional — All arguments needed for the Job to run
    notifications: new List<Notification>(),  // optional — Notifications for this Job
    useAsAuth: "..."  // optional — Id of user associated with schedule. All calls to FINBOURNE services as part of execution of this schedule will be authenticated as this  user. Can be null, in which case we&#39;ll default to that of the user  making this request
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StartJobRequest>(json);
```

- [Notification](Notification.md) — used in `Notifications`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

