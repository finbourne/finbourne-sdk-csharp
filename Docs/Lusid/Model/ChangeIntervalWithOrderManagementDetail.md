# Finbourne.Sdk.Lusid.Model.ChangeIntervalWithOrderManagementDetail

Defines a change that occured for an entity, with extra detail about the change
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Detail** | **Dictionary&lt;string, string&gt;** | Optional | Information about the particular instance of the ChangeInterval (supplied information depends on the type of Action). Contains extra detail for order management actions such as related entity ids and compliance run details. |
| **ActionDescription** | **string** | Optional | Description of the action performed on the entity. |
| **AsAtModified** | **DateTimeOffset** | Optional | The date/time of the change. |
| **UserIdModified** | **string** | Optional | The unique identifier of the user that made the change. |
| **RequestIdModified** | **string** | Optional | The unique identifier of the request that the changes were part of. |
| **ReasonModified** | **string** | Optional | The reason for an entity modification. |
| **AsAtVersionNumber** | **int** | Optional | The version number for the entity (the entity was created at version 1). This may refer to the version number of a changed related entity, not a change for the entity itself. |
| **StagedModificationIdModified** | **string** | Optional | The id of the staged modification that was approved. Will be null if the change didn&#39;t come from a staged modification. |
| **Action** | **string** | Optional | The action performed on the field. |
| **AttributeName** | **string** | Optional | The name of the field or property that has been changed. |
| **PreviousValue** | [PropertyValue](PropertyValue.md) | Optional | *No description available.* |
| **NewValue** | [PropertyValue](PropertyValue.md) | Optional | *No description available.* |
| **EffectiveRange** | [EffectiveRange](EffectiveRange.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ChangeIntervalWithOrderManagementDetail(
    detail: ,  // optional — Information about the particular instance of the ChangeInterval (supplied information depends on the type of Action). Contains extra detail for order management actions such as related entity ids and compliance run details.
    actionDescription: "...",  // optional — Description of the action performed on the entity.
    asAtModified: DateTimeOffset.Now,  // optional — The date/time of the change.
    userIdModified: "...",  // optional — The unique identifier of the user that made the change.
    requestIdModified: "...",  // optional — The unique identifier of the request that the changes were part of.
    reasonModified: "...",  // optional — The reason for an entity modification.
    asAtVersionNumber: 0,  // optional — The version number for the entity (the entity was created at version 1). This may refer to the version number of a changed related entity, not a change for the entity itself.
    stagedModificationIdModified: "...",  // optional — The id of the staged modification that was approved. Will be null if the change didn&#39;t come from a staged modification.
    action: "...",  // optional — The action performed on the field.
    attributeName: "...",  // optional — The name of the field or property that has been changed.
    previousValue: new PropertyValue(...),  // optional
    newValue: new PropertyValue(...),  // optional
    effectiveRange: new EffectiveRange(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ChangeIntervalWithOrderManagementDetail>(json);
```

- [PropertyValue](PropertyValue.md)
- [PropertyValue](PropertyValue.md)
- [EffectiveRange](EffectiveRange.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

