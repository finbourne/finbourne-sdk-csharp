# Finbourne.Sdk.Lusid.Model.AllocationEventUnbookRequest

The request used to take a half-booked Allocation Event back to Computed, cancelling what it wrote.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Reason** | **string** | Required | Why the half-booked event is being taken back to Computed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventUnbookRequest(
    reason: "..."  // required — Why the half-booked event is being taken back to Computed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventUnbookRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

