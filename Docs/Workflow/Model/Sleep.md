# Finbourne.Sdk.Workflow.Model.Sleep

Configuration for a Worker that Sleeps for a user-defined amount of time
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of worker |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new Sleep(
    type: "..."  // required — The type of worker
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Sleep>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

