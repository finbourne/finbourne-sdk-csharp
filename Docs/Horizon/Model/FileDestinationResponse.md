# Finbourne.Sdk.Horizon.Model.FileDestinationResponse

record containing details of a single file destination for a run.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | *No description available.* |
| **Path** | **string** | Required | *No description available.* |
| **Status** | **string** | Required | *No description available.* |
| **Error** | **string** | Optional | *No description available.* |
| **FailureReason** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new FileDestinationResponse(
    type: "...",  // required
    path: "...",  // required
    status: "...",  // required
    error: "...",  // optional
    failureReason: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FileDestinationResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

