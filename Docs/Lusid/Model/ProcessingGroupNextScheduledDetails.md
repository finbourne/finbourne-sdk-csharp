# Finbourne.Sdk.Lusid.Model.ProcessingGroupNextScheduledDetails

The next scheduled occurrence of a Processing Group: the next execution date after the requested date,  together with the executed (resolved) contents of the reference list the Processing Group operates over.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NextScheduleDate** | **DateTimeOffset** | Optional | The next execution date strictly after the requested date. |
| **ResolvedReferenceList** | [ReferenceList](ReferenceList.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ProcessingGroupNextScheduledDetails(
    nextScheduleDate: DateTimeOffset.Now,  // optional — The next execution date strictly after the requested date.
    resolvedReferenceList: new ReferenceList(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ProcessingGroupNextScheduledDetails>(json);
```

- [ReferenceList](ReferenceList.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

