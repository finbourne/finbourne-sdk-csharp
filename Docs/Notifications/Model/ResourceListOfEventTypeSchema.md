# Finbourne.Sdk.Notifications.Model.ResourceListOfEventTypeSchema

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;EventTypeSchema&gt;](EventTypeSchema.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |
| **NextPage** | **string** | Optional | *No description available.* |
| **PreviousPage** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new ResourceListOfEventTypeSchema(
    values: new List<EventTypeSchema>(),  // required
    href: "...",  // optional
    links: new List<Link>(),  // optional
    nextPage: "...",  // optional
    previousPage: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResourceListOfEventTypeSchema>(json);
```


## Related Models

- [EventTypeSchema](EventTypeSchema.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

