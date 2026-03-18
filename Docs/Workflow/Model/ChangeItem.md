# Finbourne.Sdk.Workflow.Model.ChangeItem

Defines a change that occured to a Task
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAtModified** | **DateTimeOffset** | Required | The AsAt time of the change |
| **UserIdModified** | **string** | Required | The User ID that performed the change |
| **RequestIdModified** | **string** | Required | The Request ID of the request that caused the change |
| **AsAtVersionNumber** | **int** | Required | The AsAt Version number |
| **Action** | **string** | Required | The Action that resulted in the change |
| **AttributeName** | **string** | Required | The name of the attribute that has been change |
| **PreviousValue** | **Object** | Optional | The value of the attribute prior to the change |
| **NewValue** | **Object** | Required | The value of the attribute following the change |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ChangeItem(
    asAtModified: DateTimeOffset.Now,  // required — The AsAt time of the change
    userIdModified: "...",  // required — The User ID that performed the change
    requestIdModified: "...",  // required — The Request ID of the request that caused the change
    asAtVersionNumber: 0,  // required — The AsAt Version number
    action: "...",  // required — The Action that resulted in the change
    attributeName: "...",  // required — The name of the attribute that has been change
    previousValue: ,  // optional — The value of the attribute prior to the change
    newValue:   // required — The value of the attribute following the change
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ChangeItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

