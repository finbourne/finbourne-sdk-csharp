# Finbourne.Sdk.Workflow.Model.LuminesceView

Configuration for a Worker that calls a Luminesce view
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of worker |
| **Name** | **string** | Required | Name of the view in Luminesce |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LuminesceView(
    type: "...",  // required — The type of worker
    name: "..."  // required — Name of the view in Luminesce
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LuminesceView>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

