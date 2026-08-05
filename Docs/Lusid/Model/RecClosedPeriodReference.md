# Finbourne.Sdk.Lusid.Model.RecClosedPeriodReference

A reference to a closed period created on a timeline when the instance was locked.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TimelineId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ClosedPeriodId** | **string** | Required | The identifier of the closed period. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecClosedPeriodReference(
    timelineId: new ResourceId(...),  // required
    closedPeriodId: "..."  // required — The identifier of the closed period.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecClosedPeriodReference>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

