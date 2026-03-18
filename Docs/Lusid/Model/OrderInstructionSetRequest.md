# Finbourne.Sdk.Lusid.Model.OrderInstructionSetRequest

A request to create or update multiple OrderInstructions.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Requests** | [List&lt;OrderInstructionRequest&gt;](OrderInstructionRequest.md) | Optional | A collection of OrderInstructionRequests. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderInstructionSetRequest(
    requests: new List<OrderInstructionRequest>()  // optional — A collection of OrderInstructionRequests.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderInstructionSetRequest>(json);
```


## Related Models

- [OrderInstructionRequest](OrderInstructionRequest.md) — used in `Requests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

