# Finbourne.Sdk.Identity.Model.UpsertMcpToolRequest

Request to create or update an MCP tool
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of the MCP tool (alphanumeric, underscore, and hyphen) |
| **Title** | **string** | Required | The title of the MCP tool |
| **Description** | **string** | Required | The description of the MCP tool |
| **Destructive** | **bool** | Optional | Whether the tool is destructive |
| **Idempotent** | **bool** | Optional | Whether the tool is idempotent |
| **OpenWorld** | **bool** | Optional | Whether the tool operates in open world |
| **ReadOnly** | **bool** | Optional | Whether the tool is read-only |
| **Parameters** | [List&lt;McpToolParameter&gt;](McpToolParameter.md) | Optional | The parameters for this MCP tool |
| **LuminescePayload** | [McpToolLuminescePayload](McpToolLuminescePayload.md) | Optional | *No description available.* |
| **SchedulerPayload** | [McpToolSchedulerPayload](McpToolSchedulerPayload.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UpsertMcpToolRequest(
    name: "...",  // required — The name of the MCP tool (alphanumeric, underscore, and hyphen)
    title: "...",  // required — The title of the MCP tool
    description: "...",  // required — The description of the MCP tool
    destructive: true,  // optional — Whether the tool is destructive
    idempotent: true,  // optional — Whether the tool is idempotent
    openWorld: true,  // optional — Whether the tool operates in open world
    readOnly: true,  // optional — Whether the tool is read-only
    parameters: new List<McpToolParameter>(),  // optional — The parameters for this MCP tool
    luminescePayload: new McpToolLuminescePayload(...),  // optional
    schedulerPayload: new McpToolSchedulerPayload(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertMcpToolRequest>(json);
```

- [McpToolParameter](McpToolParameter.md) — used in `Parameters`
- [McpToolLuminescePayload](McpToolLuminescePayload.md)
- [McpToolSchedulerPayload](McpToolSchedulerPayload.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

