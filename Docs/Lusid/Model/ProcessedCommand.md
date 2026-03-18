# Finbourne.Sdk.Lusid.Model.ProcessedCommand

The list of commands.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Description** | **string** | Required | The description of the command issued. |
| **Path** | **string** | Optional | The unique identifier for the command including the request id. |
| **UserId** | [User](User.md) | Required | *No description available.* |
| **ProcessedTime** | **DateTimeOffset** | Required | The asAt datetime that the events published by the processing of this command were committed to LUSID. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ProcessedCommand(
    description: "...",  // required — The description of the command issued.
    path: "...",  // optional — The unique identifier for the command including the request id.
    userId: new User(...),  // required
    processedTime: DateTimeOffset.Now  // required — The asAt datetime that the events published by the processing of this command were committed to LUSID.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ProcessedCommand>(json);
```

- [User](User.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

