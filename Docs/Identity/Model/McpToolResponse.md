# Finbourne.Sdk.Identity.Model.McpToolResponse

The response representation of an MCP tool
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Optional | The scope of the MCP tool |
| **Code** | **string** | Optional | The code of the MCP tool |
| **Name** | **string** | Optional | The name of the MCP tool |
| **VarVersion** | **int** | Optional | The version number of this MCP tool |
| **Title** | **string** | Optional | The title of the MCP tool |
| **Description** | **string** | Optional | The description of the MCP tool |
| **Destructive** | **bool** | Optional | Whether the tool is destructive |
| **Idempotent** | **bool** | Optional | Whether the tool is idempotent |
| **OpenWorld** | **bool** | Optional | Whether the tool operates in open world |
| **ReadOnly** | **bool** | Optional | Whether the tool is read-only |
| **Parameters** | [List&lt;McpToolParameter&gt;](McpToolParameter.md) | Optional | The parameters for this MCP tool |
| **PayloadType** | **string** | Optional | The type of payload (Luminesce or Scheduler) |
| **LuminescePayload** | [McpToolLuminescePayload](McpToolLuminescePayload.md) | Optional | *No description available.* |
| **SchedulerPayload** | [McpToolSchedulerPayload](McpToolSchedulerPayload.md) | Optional | *No description available.* |
| **CreatedAt** | **DateTimeOffset** | Optional | When the MCP tool was created |
| **CreatedBy** | **string** | Optional | Who created the MCP tool |
| **UpdatedAt** | **DateTimeOffset** | Optional | When the MCP tool was last updated |
| **UpdatedBy** | **string** | Optional | Who last updated the MCP tool |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new McpToolResponse(
    scope: "...",  // optional — The scope of the MCP tool
    code: "...",  // optional — The code of the MCP tool
    name: "...",  // optional — The name of the MCP tool
    varVersion: 0,  // optional — The version number of this MCP tool
    title: "...",  // optional — The title of the MCP tool
    description: "...",  // optional — The description of the MCP tool
    destructive: true,  // optional — Whether the tool is destructive
    idempotent: true,  // optional — Whether the tool is idempotent
    openWorld: true,  // optional — Whether the tool operates in open world
    readOnly: true,  // optional — Whether the tool is read-only
    parameters: new List<McpToolParameter>(),  // optional — The parameters for this MCP tool
    payloadType: "...",  // optional — The type of payload (Luminesce or Scheduler)
    luminescePayload: new McpToolLuminescePayload(...),  // optional
    schedulerPayload: new McpToolSchedulerPayload(...),  // optional
    createdAt: DateTimeOffset.Now,  // optional — When the MCP tool was created
    createdBy: "...",  // optional — Who created the MCP tool
    updatedAt: DateTimeOffset.Now,  // optional — When the MCP tool was last updated
    updatedBy: "..."  // optional — Who last updated the MCP tool
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<McpToolResponse>(json);
```

- [McpToolParameter](McpToolParameter.md) — used in `Parameters`
- [McpToolLuminescePayload](McpToolLuminescePayload.md)
- [McpToolSchedulerPayload](McpToolSchedulerPayload.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

