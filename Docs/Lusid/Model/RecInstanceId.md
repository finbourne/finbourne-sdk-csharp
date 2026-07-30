# Finbourne.Sdk.Lusid.Model.RecInstanceId

Identifies a rec instance, and how it was created.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstanceIdType** | **string** | Required | How the instance was created. Available values: WorkflowServiceTaskId, Manual. |
| **InstanceIdValue** | **string** | Required | The instance identifier value (a GUID). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecInstanceId(
    instanceIdType: "...",  // required — How the instance was created. Available values: WorkflowServiceTaskId, Manual.
    instanceIdValue: "..."  // required — The instance identifier value (a GUID).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecInstanceId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

