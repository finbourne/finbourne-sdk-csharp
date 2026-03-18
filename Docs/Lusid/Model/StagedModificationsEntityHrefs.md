# Finbourne.Sdk.Lusid.Model.StagedModificationsEntityHrefs

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WhenStaged** | **string** | Optional | The specific Uniform Resource Identifier (URI) for the staged modification change at the time when the change was requested. |
| **Preview** | **string** | Optional | The specific Uniform Resource Identifier (URI) for the preview of staged modification change once applied. |
| **Latest** | **string** | Optional | The specific Uniform Resource Identifier (URI) for the staged modification at latest time. |
| **WhenClosed** | **string** | Optional | The specific Uniform Resource Identifier (URI) for the staged modification after it has been applied. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagedModificationsEntityHrefs(
    whenStaged: "...",  // optional — The specific Uniform Resource Identifier (URI) for the staged modification change at the time when the change was requested.
    preview: "...",  // optional — The specific Uniform Resource Identifier (URI) for the preview of staged modification change once applied.
    latest: "...",  // optional — The specific Uniform Resource Identifier (URI) for the staged modification at latest time.
    whenClosed: "...",  // optional — The specific Uniform Resource Identifier (URI) for the staged modification after it has been applied.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagedModificationsEntityHrefs>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

