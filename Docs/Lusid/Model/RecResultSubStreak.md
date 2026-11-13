# Finbourne.Sdk.Lusid.Model.RecResultSubStreak

The part of a streak, ending at this result, over which a stricter condition held: same difference, or open.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Age** | **string** | Required | The ISO 8601 duration from the startResult&#39;s asAtFirstSeen to the runAsAt of this result&#39;s latest run. Zero when the predecessor does not extend the sub-streak. |
| **CountInstances** | **int?** | Optional | The number of instances in the sub-streak, including this one. Null when the predecessor does not extend the sub-streak; otherwise 2 or more. |
| **StartResult** | [RecAgedResult](RecAgedResult.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultSubStreak(
    age: "...",  // required — The ISO 8601 duration from the startResult&#39;s asAtFirstSeen to the runAsAt of this result&#39;s latest run. Zero when the predecessor does not extend the sub-streak.
    countInstances: 0,  // optional — The number of instances in the sub-streak, including this one. Null when the predecessor does not extend the sub-streak; otherwise 2 or more.
    startResult: new RecAgedResult(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultSubStreak>(json);
```

- [RecAgedResult](RecAgedResult.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

