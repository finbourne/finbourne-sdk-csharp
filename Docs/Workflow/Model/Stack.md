# Finbourne.Sdk.Workflow.Model.Stack

Information pertaining to the Tasks Stack if one is present
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MemberAddedAsAt** | **DateTimeOffset** | Optional | When the Task was added to the Stack |
| **StackOpenedAsAt** | **DateTimeOffset** | Optional | When the Stack was opened |
| **StackClosedAsAt** | **DateTimeOffset?** | Optional | When the Stack was closed |
| **StackMembershipType** | **string** | Optional | Whether the task is the Lead task of the Stack or a Member within the Stack |
| **StackStatus** | **string** | Optional | Status of the Stack (Open/Closed) |
| **LeadTaskId** | **Guid** | Optional | ID of the Lead Task |
| **LeadTaskState** | **string** | Optional | State of the Lead Task |
| **TasksInStack** | **int** | Optional | Number of Tasks in the Stack |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new Stack(
    memberAddedAsAt: DateTimeOffset.Now,  // optional — When the Task was added to the Stack
    stackOpenedAsAt: DateTimeOffset.Now,  // optional — When the Stack was opened
    stackClosedAsAt: DateTimeOffset.Now,  // optional — When the Stack was closed
    stackMembershipType: "...",  // optional — Whether the task is the Lead task of the Stack or a Member within the Stack
    stackStatus: "...",  // optional — Status of the Stack (Open/Closed)
    leadTaskId: "...",  // optional — ID of the Lead Task
    leadTaskState: "...",  // optional — State of the Lead Task
    tasksInStack: 0  // optional — Number of Tasks in the Stack
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Stack>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

