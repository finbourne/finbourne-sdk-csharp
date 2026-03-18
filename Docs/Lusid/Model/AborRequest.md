# Finbourne.Sdk.Lusid.Model.AborRequest

The request used to create an Abor.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code given for the Abor. |
| **DisplayName** | **string** | Required | The name of the Abor. |
| **Description** | **string** | Optional | The description for the Abor. |
| **PortfolioIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | The list with the portfolio ids which are part of the Abor. Note: These must all have the same base currency. |
| **AborConfigurationId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Abor. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AborRequest(
    code: "...",  // required — The code given for the Abor.
    displayName: "...",  // required — The name of the Abor.
    description: "...",  // optional — The description for the Abor.
    portfolioIds: new List<PortfolioEntityId>(),  // required — The list with the portfolio ids which are part of the Abor. Note: These must all have the same base currency.
    aborConfigurationId: new ResourceId(...),  // required
    properties: new Property(...)  // optional — A set of properties for the Abor.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AborRequest>(json);
```

- [PortfolioEntityId](PortfolioEntityId.md) — used in `PortfolioIds`
- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

