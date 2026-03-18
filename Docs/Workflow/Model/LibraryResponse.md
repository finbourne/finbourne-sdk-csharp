# Finbourne.Sdk.Workflow.Model.LibraryResponse

Readonly configuration for any Library Worker
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of worker |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LibraryResponse(
    type: "..."  // optional — The type of worker
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LibraryResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

