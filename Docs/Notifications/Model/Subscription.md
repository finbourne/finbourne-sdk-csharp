# Finbourne.Sdk.Notifications.Model.Subscription

A subscription object
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | The name of the subscription |
| **Description** | **string** | Optional | The summary of the services provided by the subscription |
| **Status** | **string** | Required | The current status of the subscription |
| **MatchingPattern** | [MatchingPattern](MatchingPattern.md) | Required | *No description available.* |
| **CreatedAt** | **DateTimeOffset** | Required | The time at which the subscription was made |
| **UserIdCreated** | **string** | Required | The user who made the subscription |
| **ModifiedAt** | **DateTimeOffset** | Required | The time at which the subscription was last modified |
| **UserIdModified** | **string** | Required | The user who last modified the subscription |
| **UseAsAuth** | **string** | Required | The user to use as auth for the subscription |
| **Href** | **string** | Optional | A URI for retrieving this subscription |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new Subscription(
    id: new ResourceId(...),  // required
    displayName: "...",  // required — The name of the subscription
    description: "...",  // optional — The summary of the services provided by the subscription
    status: "...",  // required — The current status of the subscription
    matchingPattern: new MatchingPattern(...),  // required
    createdAt: DateTimeOffset.Now,  // required — The time at which the subscription was made
    userIdCreated: "...",  // required — The user who made the subscription
    modifiedAt: DateTimeOffset.Now,  // required — The time at which the subscription was last modified
    userIdModified: "...",  // required — The user who last modified the subscription
    useAsAuth: "...",  // required — The user to use as auth for the subscription
    href: "..."  // optional — A URI for retrieving this subscription
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Subscription>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [MatchingPattern](MatchingPattern.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

