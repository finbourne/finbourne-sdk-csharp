# Finbourne.Sdk.Lusid.Model.BucketingSchedule

A schedule for dates
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Tenor** | **string** | Optional | Rolling tenor |
| **RollDirection** | **string** | Optional | Optional direction in which the bucketing dates are rolled out from the schedule tenor.  Supported string (enumeration) values are: [ForwardFromStart, BackwardFromEnd].  If absent (and StubType is also absent), the pre-existing date generation behaviour is used. Available values: ForwardFromStart, BackwardFromEnd. |
| **StubType** | **string** | Optional | Optional treatment of the irregular (stub) period when the window length is not an exact multiple of the tenor.  Supported string (enumeration) values are: [ShortStub, LongStub].  If absent (and RollDirection is also absent), the pre-existing date generation behaviour is used. Available values: ShortStub, LongStub. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketingSchedule(
    tenor: "...",  // optional — Rolling tenor
    rollDirection: "...",  // optional — Optional direction in which the bucketing dates are rolled out from the schedule tenor.  Supported string (enumeration) values are: [ForwardFromStart, BackwardFromEnd].  If absent (and StubType is also absent), the pre-existing date generation behaviour is used. Available values: ForwardFromStart, BackwardFromEnd.
    stubType: "..."  // optional — Optional treatment of the irregular (stub) period when the window length is not an exact multiple of the tenor.  Supported string (enumeration) values are: [ShortStub, LongStub].  If absent (and RollDirection is also absent), the pre-existing date generation behaviour is used. Available values: ShortStub, LongStub.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketingSchedule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

