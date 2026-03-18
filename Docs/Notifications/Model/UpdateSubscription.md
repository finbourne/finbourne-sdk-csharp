# Finbourne.Sdk.Notifications.Model.UpdateSubscription

The information required to update a subscription
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the subscription |
| **Description** | **string** | Optional | The summary of the services provided by the subscription |
| **Status** | **string** | Required | The current status of the subscription. Possible values are: Active, Inactive |
| **MatchingPattern** | [MatchingPattern](MatchingPattern.md) | Required | *No description available.* |
| **UseAsAuth** | **string** | Optional | Id of user associated with subscription. All events associated with  the subscription will use this user to check entitlements against  the resource to send a notification. Can be null, in which case  we&#39;ll default to that of the user making this request |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new UpdateSubscription(
    displayName: "...",  // required — The name of the subscription
    description: "...",  // optional — The summary of the services provided by the subscription
    status: "...",  // required — The current status of the subscription. Possible values are: Active, Inactive
    matchingPattern: new MatchingPattern(...),  // required
    useAsAuth: "..."  // optional — Id of user associated with subscription. All events associated with  the subscription will use this user to check entitlements against  the resource to send a notification. Can be null, in which case  we&#39;ll default to that of the user making this request
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateSubscription>(json);
```

- [MatchingPattern](MatchingPattern.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

