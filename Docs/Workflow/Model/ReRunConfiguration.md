# Finbourne.Sdk.Workflow.Model.ReRunConfiguration

Defines how re-run results for a given (child) TaskDefinitionId should be reconciled against existing (non-terminal) child tasks of the same parent Task instance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaskDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ResultsRecurring** | [ResultsRecurringConfiguration](ResultsRecurringConfiguration.md) | Required | *No description available.* |
| **ResultsNotRecurring** | [ResultsNotRecurringConfiguration](ResultsNotRecurringConfiguration.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ReRunConfiguration(
    taskDefinitionId: new ResourceId(...),  // required
    resultsRecurring: new ResultsRecurringConfiguration(...),  // required
    resultsNotRecurring: new ResultsNotRecurringConfiguration(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReRunConfiguration>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResultsRecurringConfiguration](ResultsRecurringConfiguration.md)
- [ResultsNotRecurringConfiguration](ResultsNotRecurringConfiguration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

