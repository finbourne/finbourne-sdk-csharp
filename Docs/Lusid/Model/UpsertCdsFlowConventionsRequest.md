# Finbourne.Sdk.Lusid.Model.UpsertCdsFlowConventionsRequest

CDS Flow convention that is to be stored in the convention data store.  Only one of these must be present.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CdsFlowConventions** | [CdsFlowConventions](CdsFlowConventions.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertCdsFlowConventionsRequest(
    cdsFlowConventions: new CdsFlowConventions(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertCdsFlowConventionsRequest>(json);
```


## Related Models

- [CdsFlowConventions](CdsFlowConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

