# Finbourne.Sdk.Lusid.Model.GetTransferRequest

The transfer to read. Every part of its identity is required: a transfer is identified by its scope, its code  and the two portfolios its in and out transaction are booked into.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransferId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PortfolioIdOut** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PortfolioIdIn** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PropertyKeys** | **List&lt;string&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GetTransferRequest(
    transferId: new ResourceId(...),  // required
    portfolioIdOut: new ResourceId(...),  // required
    portfolioIdIn: new ResourceId(...),  // required
    propertyKeys:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GetTransferRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

