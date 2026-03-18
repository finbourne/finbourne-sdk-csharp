# Finbourne.Sdk.Workflow.Model.LuminesceViewResponse

Readonly configuration for a Worker that calls a Luminesce view
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of worker |
| **Name** | **string** | Optional | Name of the view in Luminesce |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LuminesceViewResponse(
    type: "...",  // optional — The type of worker
    name: "..."  // optional — Name of the view in Luminesce
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LuminesceViewResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

