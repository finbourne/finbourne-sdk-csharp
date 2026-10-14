# Finbourne.Sdk.Lusid.Model.AllocationEventBookingWarning

One validation rule a booking was allowed to proceed through under the map's policy.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Optional | The rule that was allowed through, for instance OverCall. |
| **Detail** | **string** | Optional | What the rule found. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventBookingWarning(
    code: "...",  // optional — The rule that was allowed through, for instance OverCall.
    detail: "..."  // optional — What the rule found.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventBookingWarning>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

