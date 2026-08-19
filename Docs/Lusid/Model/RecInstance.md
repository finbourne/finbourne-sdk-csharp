# Finbourne.Sdk.Lusid.Model.RecInstance

The expanded view of a rec instance: its identity, lifecycle status, lock state, closed periods  (for Closed Period windows) and the time-series of runs in the run log.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [RecInstanceId](RecInstanceId.md) | Required | *No description available.* |
| **RecDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **AsAtInstantiated** | **DateTimeOffset** | Required | The asAt datetime at which the instance was first created. |
| **Status** | **string** | Required | The instance-level lifecycle rollup. Available values: Running, Failures, ReviewAndApproval, AllApproved, Locked. |
| **AsAtLocked** | **DateTimeOffset?** | Optional | The wall-clock time the lock action was performed. Null when the instance has not been locked. |
| **DatesLocked** | [RecDatesReconciled](RecDatesReconciled.md) | Optional | *No description available.* |
| **ClosedPeriods** | [RecClosedPeriods](RecClosedPeriods.md) | Optional | *No description available.* |
| **RunLog** | [List&lt;RecRunLogEntry&gt;](RecRunLogEntry.md) | Required | A chronologically ordered list of all runs on the instance. Always contains at least one entry. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecInstance(
    id: new RecInstanceId(...),  // required
    recDefinitionId: new ResourceId(...),  // required
    asAtInstantiated: DateTimeOffset.Now,  // required — The asAt datetime at which the instance was first created.
    status: "...",  // required — The instance-level lifecycle rollup. Available values: Running, Failures, ReviewAndApproval, AllApproved, Locked.
    asAtLocked: DateTimeOffset.Now,  // optional — The wall-clock time the lock action was performed. Null when the instance has not been locked.
    datesLocked: new RecDatesReconciled(...),  // optional
    closedPeriods: new RecClosedPeriods(...),  // optional
    runLog: new List<RecRunLogEntry>(),  // required — A chronologically ordered list of all runs on the instance. Always contains at least one entry.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecInstance>(json);
```


## Related Models

- [RecInstanceId](RecInstanceId.md)
- [ResourceId](ResourceId.md)
- [RecDatesReconciled](RecDatesReconciled.md)
- [RecClosedPeriods](RecClosedPeriods.md)
- [RecRunLogEntry](RecRunLogEntry.md) — used in `RunLog`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

