# Finbourne.Sdk.Lusid.Model.AddressDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Optional | The display name of the address key. |
| **Type** | **string** | Optional | The available values are: String, Int, Decimal, DateTime, Boolean, ResultValue, Result0D, Json |
| **Description** | **string** | Optional | The description for this result. |
| **LifeCycleStatus** | **string** | Optional | What is the status of the address path. If it is not Production then it might be removed at some point in the future.  See the removal date for the likely timing of that if any. |
| **RemovalDate** | **DateTimeOffset?** | Optional | If the life-cycle status of the address is Deprecated then this is the date at which support of the address will be suspended.  After that date it will be removed at the earliest possible point subject to any specific contractual support and development constraints. |
| **DocumentationLink** | **string** | Optional | Contains a link to the documentation for this AddressDefinition in KnowledgeBase. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AddressDefinition(
    displayName: "...",  // optional — The display name of the address key.
    type: "...",  // optional — The available values are: String, Int, Decimal, DateTime, Boolean, ResultValue, Result0D, Json
    description: "...",  // optional — The description for this result.
    lifeCycleStatus: "...",  // optional — What is the status of the address path. If it is not Production then it might be removed at some point in the future.  See the removal date for the likely timing of that if any.
    removalDate: DateTimeOffset.Now,  // optional — If the life-cycle status of the address is Deprecated then this is the date at which support of the address will be suspended.  After that date it will be removed at the earliest possible point subject to any specific contractual support and development constraints.
    documentationLink: "..."  // optional — Contains a link to the documentation for this AddressDefinition in KnowledgeBase.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AddressDefinition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

