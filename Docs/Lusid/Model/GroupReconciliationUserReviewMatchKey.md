# Finbourne.Sdk.Lusid.Model.GroupReconciliationUserReviewMatchKey

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MatchKey** | **string** | Required | The match key of the reconciliation result. |
| **UserId** | **string** | Optional | Id of the user who made a User Review input. |
| **AsAtAdded** | **DateTimeOffset** | Optional | The timestamp of the added User Review input. |
| **AsAtInvalid** | **DateTimeOffset** | Optional | The timestamp when User Review input became invalid e.g. because of the different attribute values within the new run. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationUserReviewMatchKey(
    matchKey: "...",  // required — The match key of the reconciliation result.
    userId: "...",  // optional — Id of the user who made a User Review input.
    asAtAdded: DateTimeOffset.Now,  // optional — The timestamp of the added User Review input.
    asAtInvalid: DateTimeOffset.Now  // optional — The timestamp when User Review input became invalid e.g. because of the different attribute values within the new run.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationUserReviewMatchKey>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

