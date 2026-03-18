# Finbourne.Sdk.Workflow.Model.TaskFieldDefinition

Defines a Task Definition Field
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of this Field |
| **Type** | **string** | Required | The value type for the field. Available values are: \&quot;String\&quot;, \&quot;Decimal\&quot;, \&quot;DateTime\&quot;, \&quot;Boolean\&quot;) |
| **ReadOnlyStates** | [ReadOnlyStates](ReadOnlyStates.md) | Optional | *No description available.* |
| **ValueConstraints** | [ValueConstraints](ValueConstraints.md) | Optional | *No description available.* |
| **DisplayName** | **string** | Optional | Display name for field definition |
| **Description** | **string** | Optional | Description for field definition |
| **Category** | **string** | Optional | Category for field definition |
| **ContainsUrl** | **bool?** | Optional | Field contains url |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TaskFieldDefinition(
    name: "...",  // required — The name of this Field
    type: "...",  // required — The value type for the field. Available values are: \&quot;String\&quot;, \&quot;Decimal\&quot;, \&quot;DateTime\&quot;, \&quot;Boolean\&quot;)
    readOnlyStates: new ReadOnlyStates(...),  // optional
    valueConstraints: new ValueConstraints(...),  // optional
    displayName: "...",  // optional — Display name for field definition
    description: "...",  // optional — Description for field definition
    category: "...",  // optional — Category for field definition
    containsUrl: true  // optional — Field contains url
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaskFieldDefinition>(json);
```

- [ReadOnlyStates](ReadOnlyStates.md)
- [ValueConstraints](ValueConstraints.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

