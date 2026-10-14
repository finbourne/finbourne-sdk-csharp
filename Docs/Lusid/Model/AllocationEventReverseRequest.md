# Finbourne.Sdk.Lusid.Model.AllocationEventReverseRequest

The request used to reverse a booked Allocation Event: why, and when the mirror postings are dated.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Reason** | **string** | Required | Why the booked event is being reversed. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The date to post the mirror entries at. Defaults to the original event date unless that period is closed, when it defaults to the current date. |
| **Backdated** | **bool** | Optional | Whether to post the mirror entries at the original event date even when that period is closed. Defaults to false. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventReverseRequest(
    reason: "...",  // required — Why the booked event is being reversed.
    effectiveAt: DateTimeOffset.Now,  // optional — The date to post the mirror entries at. Defaults to the original event date unless that period is closed, when it defaults to the current date.
    backdated: true  // optional — Whether to post the mirror entries at the original event date even when that period is closed. Defaults to false.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventReverseRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

