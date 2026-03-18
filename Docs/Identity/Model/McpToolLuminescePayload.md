# Finbourne.Sdk.Identity.Model.McpToolLuminescePayload

Payload data for a Luminesce query MCP tool
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Query** | **string** | Required | The Luminesce query to execute |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new McpToolLuminescePayload(
    query: "..."  // required — The Luminesce query to execute
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<McpToolLuminescePayload>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

