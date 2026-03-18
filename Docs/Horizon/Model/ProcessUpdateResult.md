# Finbourne.Sdk.Horizon.Model.ProcessUpdateResult

Shows details relevant to update events for a query
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Domain** | **string** | Required | *No description available.* |
| **EntryId** | **string** | Required | *No description available.* |
| **ProcessName** | **string** | Required | *No description available.* |
| **RunId** | **string** | Required | *No description available.* |
| **EntryDate** | **DateTimeOffset** | Required | *No description available.* |
| **Status** | **string** | Required | *No description available.* |
| **Message** | **string** | Required | *No description available.* |
| **SchemaVersion** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ProcessUpdateResult(
    domain: "...",  // required
    entryId: "...",  // required
    processName: "...",  // required
    runId: "...",  // required
    entryDate: DateTimeOffset.Now,  // required
    status: "...",  // required
    message: "...",  // required
    schemaVersion: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ProcessUpdateResult>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

