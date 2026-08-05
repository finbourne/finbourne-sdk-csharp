# Finbourne.Sdk.Lusid.Model.TransitionRecInstanceRequest

The request to apply a lifecycle transition (re-run, lock or unlock) to a rec instance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Action** | **string** | Required | The transition to apply. Available values: ReRun, Lock, Unlock. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransitionRecInstanceRequest(
    action: "..."  // required — The transition to apply. Available values: ReRun, Lock, Unlock.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransitionRecInstanceRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

