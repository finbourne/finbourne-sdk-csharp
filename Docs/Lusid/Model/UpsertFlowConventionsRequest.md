# Finbourne.Sdk.Lusid.Model.UpsertFlowConventionsRequest

Flow conventions that is to be stored in the convention data store.  Only one of these must be present.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FlowConventions** | [FlowConventions](FlowConventions.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertFlowConventionsRequest(
    flowConventions: new FlowConventions(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertFlowConventionsRequest>(json);
```


## Related Models

- [FlowConventions](FlowConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

