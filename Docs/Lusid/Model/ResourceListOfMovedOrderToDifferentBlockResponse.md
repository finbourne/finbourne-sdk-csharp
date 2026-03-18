# Finbourne.Sdk.Lusid.Model.ResourceListOfMovedOrderToDifferentBlockResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;MovedOrderToDifferentBlockResponse&gt;](MovedOrderToDifferentBlockResponse.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |
| **NextPage** | **string** | Optional | *No description available.* |
| **PreviousPage** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResourceListOfMovedOrderToDifferentBlockResponse(
    values: new List<MovedOrderToDifferentBlockResponse>(),  // required
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
var instance = JsonConvert.DeserializeObject<ResourceListOfMovedOrderToDifferentBlockResponse>(json);
```


## Related Models

- [MovedOrderToDifferentBlockResponse](MovedOrderToDifferentBlockResponse.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

