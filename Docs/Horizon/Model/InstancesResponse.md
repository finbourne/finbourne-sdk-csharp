# Finbourne.Sdk.Horizon.Model.InstancesResponse

record containing a list of instances.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Instances** | [List&lt;InstanceResponse&gt;](InstanceResponse.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new InstancesResponse(
    instances: new List<InstanceResponse>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstancesResponse>(json);
```


## Related Models

- [InstanceResponse](InstanceResponse.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

