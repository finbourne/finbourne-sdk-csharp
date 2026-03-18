# Finbourne.Sdk.Scheduler.Model.ResourceListOfRepository

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;Repository&gt;](Repository.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |
| **NextPage** | **string** | Optional | *No description available.* |
| **PreviousPage** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new ResourceListOfRepository(
    values: new List<Repository>(),  // required
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
var instance = JsonConvert.DeserializeObject<ResourceListOfRepository>(json);
```


## Related Models

- [Repository](Repository.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

