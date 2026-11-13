# Finbourne.Sdk.Lusid.Model.RecResultStreak

The run of consecutive instances, ending at this result, in which the same result was produced, with its  difference and open sub-streaks.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Predecessor** | [RecResultStreakPredecessor](RecResultStreakPredecessor.md) | Required | *No description available.* |
| **Age** | **string** | Required | The ISO 8601 duration from the startResult&#39;s asAtFirstSeen to the runAsAt of this result&#39;s latest run. Always positive. |
| **CountInstances** | **int** | Required | The number of instances in the streak, including this one. Always 2 or more. |
| **StartResult** | [RecAgedResult](RecAgedResult.md) | Required | *No description available.* |
| **DifferenceStreak** | [RecResultSubStreak](RecResultSubStreak.md) | Required | *No description available.* |
| **OpenStreak** | [RecResultSubStreak](RecResultSubStreak.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultStreak(
    predecessor: new RecResultStreakPredecessor(...),  // required
    age: "...",  // required — The ISO 8601 duration from the startResult&#39;s asAtFirstSeen to the runAsAt of this result&#39;s latest run. Always positive.
    countInstances: 0,  // required — The number of instances in the streak, including this one. Always 2 or more.
    startResult: new RecAgedResult(...),  // required
    differenceStreak: new RecResultSubStreak(...),  // required
    openStreak: new RecResultSubStreak(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultStreak>(json);
```


## Related Models

- [RecResultStreakPredecessor](RecResultStreakPredecessor.md)
- [RecAgedResult](RecAgedResult.md)
- [RecResultSubStreak](RecResultSubStreak.md)
- [RecResultSubStreak](RecResultSubStreak.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

