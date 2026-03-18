# Finbourne.Sdk.Identity.Model.McpToolParameter

A parameter definition for an MCP tool
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of the parameter (identifier format) |
| **DataType** | **string** | Required | The data type of the parameter |
| **Description** | **string** | Optional | A description of what the parameter is used for |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new McpToolParameter(
    name: "...",  // required — The name of the parameter (identifier format)
    dataType: "...",  // required — The data type of the parameter
    description: "..."  // optional — A description of what the parameter is used for
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<McpToolParameter>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

