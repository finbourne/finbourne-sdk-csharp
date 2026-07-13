# Finbourne.Sdk.Lusid.Model.UpsertSubscriptionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Subscription** | [SubscriptionDefinition](SubscriptionDefinition.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertSubscriptionRequest(
    subscription: new SubscriptionDefinition(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertSubscriptionRequest>(json);
```


## Related Models

- [SubscriptionDefinition](SubscriptionDefinition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

