# Finbourne.Sdk.Lusid.Model.SideConfigurationData

Configuration needed to define a side. Sides are referenced by Label. Beyond that, other properties  can be used to reference either transaction fields, or transaction properties.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Side** | **string** | Required | The side&#39;s label. |
| **Security** | **string** | Required | The security, or instrument. |
| **Currency** | **string** | Required | The currency. |
| **Rate** | **string** | Required | The rate. |
| **Units** | **string** | Required | The units. |
| **Amount** | **string** | Required | The amount. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SideConfigurationData(
    side: "...",  // required — The side&#39;s label.
    security: "...",  // required — The security, or instrument.
    currency: "...",  // required — The currency.
    rate: "...",  // required — The rate.
    units: "...",  // required — The units.
    amount: "...",  // required — The amount.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SideConfigurationData>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

