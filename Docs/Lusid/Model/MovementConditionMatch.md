# Finbourne.Sdk.Lusid.Model.MovementConditionMatch

The outcome of one movement's condition for a transaction. Reported per movement rather than keyed by  movement, because a transaction type may configure several movements that share a side and have no name.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MovementName** | **string** | Optional | The name of the movement, or null if the movement is unnamed. |
| **Side** | **string** | Required | The side the movement is configured against. |
| **ConditionMatched** | **bool** | Optional | Whether the movement&#39;s condition was satisfied by this transaction. A movement with no condition always matches. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MovementConditionMatch(
    movementName: "...",  // optional — The name of the movement, or null if the movement is unnamed.
    side: "...",  // required — The side the movement is configured against.
    conditionMatched: true  // optional — Whether the movement&#39;s condition was satisfied by this transaction. A movement with no condition always matches.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MovementConditionMatch>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

