# Finbourne.Sdk.Lusid.Model.PostCloseActivitiesRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PostCloseActivities** | [List&lt;PostCloseActivity&gt;](PostCloseActivity.md) | Required | A collection of post-close activities. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PostCloseActivitiesRequest(
    postCloseActivities: new List<PostCloseActivity>()  // required — A collection of post-close activities.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PostCloseActivitiesRequest>(json);
```


## Related Models

- [PostCloseActivity](PostCloseActivity.md) — used in `PostCloseActivities`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

