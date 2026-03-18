# Finbourne.Sdk.Lusid.Model.DeleteInstrumentsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **AsAt** | **DateTimeOffset** | Required | The as-at datetime at which the instrument was deleted. |
| **Staged** | [Dictionary&lt;string, StagedModificationsInfo&gt;](StagedModificationsInfo.md) | Optional | Information about the pending staged modifications for the current entity. *(read-only)* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DeleteInstrumentsResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    asAt: DateTimeOffset.Now,  // required — The as-at datetime at which the instrument was deleted.
    staged: new StagedModificationsInfo(...),  // optional — Information about the pending staged modifications for the current entity.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeleteInstrumentsResponse>(json);
```

- [StagedModificationsInfo](StagedModificationsInfo.md) — used in `Staged`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

