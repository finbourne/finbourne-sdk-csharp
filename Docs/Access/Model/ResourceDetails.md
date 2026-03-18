# Finbourne.Sdk.Access.Model.ResourceDetails

Details about the resource being requested that may be pertinent to the entitlement evaluation
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **Dictionary&lt;string, string&gt;** | Required | The identifier of the resource being evaluated |
| **Metadata** | **Dictionary&lt;string, List&lt;EntitlementMetadata&gt;&gt;** | Optional | Any metadata associated with the resource being requested |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new ResourceDetails(
    id: ,  // required — The identifier of the resource being evaluated
    metadata:   // optional — Any metadata associated with the resource being requested
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResourceDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

