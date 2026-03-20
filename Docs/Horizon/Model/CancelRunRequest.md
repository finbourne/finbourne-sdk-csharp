# Finbourne.Sdk.Horizon.Model.CancelRunRequest

A request to cancel the specified instance execution.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunIds** | **List&lt;string&gt;** | Required | The instance run ids to be cancelled. |
| **Message** | **string** | Optional | The user provided message as to why the instance executions were cancelled. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new CancelRunRequest(
    runIds: ,  // required — The instance run ids to be cancelled.
    message: "..."  // optional — The user provided message as to why the instance executions were cancelled.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CancelRunRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

