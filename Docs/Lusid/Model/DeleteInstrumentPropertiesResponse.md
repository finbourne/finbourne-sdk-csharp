# Finbourne.Sdk.Lusid.Model.DeleteInstrumentPropertiesResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset** | Required | The as-at datetime at which properties were deleted. |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DeleteInstrumentPropertiesResponse(
    asAt: DateTimeOffset.Now,  // required — The as-at datetime at which properties were deleted.
    stagedModifications: new StagedModificationsInfo(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeleteInstrumentPropertiesResponse>(json);
```

- [StagedModificationsInfo](StagedModificationsInfo.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

