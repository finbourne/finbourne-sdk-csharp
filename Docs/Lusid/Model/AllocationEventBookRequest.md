# Finbourne.Sdk.Lusid.Model.AllocationEventBookRequest

The request used to book a computed Allocation Event: the reference under which its shares were posted.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BookingReference** | **string** | Required | The reference under which the computed shares were posted, for instance a journal entry code. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventBookRequest(
    bookingReference: "..."  // required — The reference under which the computed shares were posted, for instance a journal entry code.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventBookRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

