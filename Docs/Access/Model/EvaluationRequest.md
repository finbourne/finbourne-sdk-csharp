# Finbourne.Sdk.Access.Model.EvaluationRequest

Specification for a server side evaluation of entitlement.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Request** | [RequestDetails](RequestDetails.md) | Required | *No description available.* |
| **Resource** | [ResourceDetails](ResourceDetails.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new EvaluationRequest(
    request: new RequestDetails(...),  // required
    resource: new ResourceDetails(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EvaluationRequest>(json);
```


## Related Models

- [RequestDetails](RequestDetails.md)
- [ResourceDetails](ResourceDetails.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

