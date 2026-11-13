# Finbourne.Sdk.Lusid.Model.RecResultStreakPredecessor

The same result in the previous instance, and which streaks it extends.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Result** | [RecAgedResult](RecAgedResult.md) | Required | *No description available.* |
| **StreakTypes** | **List&lt;string&gt;** | Required | Which streaks the predecessor extends: always Core, and Difference if the aggregate rule differences are unchanged. Open is not set yet. Available values: Core, Difference, Open. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultStreakPredecessor(
    result: new RecAgedResult(...),  // required
    streakTypes:   // required — Which streaks the predecessor extends: always Core, and Difference if the aggregate rule differences are unchanged. Open is not set yet. Available values: Core, Difference, Open.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultStreakPredecessor>(json);
```


## Related Models

- [RecAgedResult](RecAgedResult.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

