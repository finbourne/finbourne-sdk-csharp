# Finbourne.Sdk.Lusid.Model.AllocationEventBookRequest

The request used to book a computed Allocation Event: the reference under which its shares are posted, and  whether to only show what would be posted.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BookingReference** | **string** | Required | The reference under which the computed shares were posted, for instance a journal entry code. |
| **DryRun** | **bool** | Optional | Whether to only build and return the posting plan without writing anything. Defaults to false. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventBookRequest(
    bookingReference: "...",  // required — The reference under which the computed shares were posted, for instance a journal entry code.
    dryRun: true  // optional — Whether to only build and return the posting plan without writing anything. Defaults to false.
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

