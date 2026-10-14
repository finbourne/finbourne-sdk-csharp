# Finbourne.Sdk.Lusid.Model.AllocationEventBookingError

One posting a booking could not write.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Optional | The rule or write step that failed, for instance WriteFailed. |
| **Id** | **string** | Optional | The identifier of the posting that could not be written. |
| **Message** | **string** | Optional | What went wrong. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventBookingError(
    code: "...",  // optional — The rule or write step that failed, for instance WriteFailed.
    id: "...",  // optional — The identifier of the posting that could not be written.
    message: "..."  // optional — What went wrong.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventBookingError>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

