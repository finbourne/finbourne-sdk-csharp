# Finbourne.Sdk.Drive.Model.PagedResourceListOfStorageObject

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NextPage** | **string** | Optional | *No description available.* |
| **PreviousPage** | **string** | Optional | *No description available.* |
| **Values** | [List&lt;StorageObject&gt;](StorageObject.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Drive.Model;

var instance = new PagedResourceListOfStorageObject(
    nextPage: "...",  // optional
    previousPage: "...",  // optional
    values: new List<StorageObject>(),  // required
    href: "...",  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PagedResourceListOfStorageObject>(json);
```

- [StorageObject](StorageObject.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

