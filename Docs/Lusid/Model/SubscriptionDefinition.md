# Finbourne.Sdk.Lusid.Model.SubscriptionDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | *No description available.* |
| **Code** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TimelineId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **AddressKeys** | **List&lt;string&gt;** | Optional | The set of addresses the subscriber wishes to receive. |
| **ByTaxLots** | **bool** | Optional | *No description available.* |
| **StartEffectiveAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **EndEffectiveAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **StartAsAt** | **DateTimeOffset?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SubscriptionDefinition(
    scope: "...",  // required
    code: "...",  // required
    displayName: "...",  // optional
    description: "...",  // optional
    portfolioId: new ResourceId(...),  // required
    timelineId: new ResourceId(...),  // optional
    addressKeys: ,  // optional — The set of addresses the subscriber wishes to receive.
    byTaxLots: true,  // optional
    startEffectiveAt: DateTimeOffset.Now,  // optional
    endEffectiveAt: DateTimeOffset.Now,  // optional
    startAsAt: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SubscriptionDefinition>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

