# Finbourne.Sdk.Lusid.Model.SideDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Side** | **string** | Required | A unique label identifying the side definition. |
| **Security** | **string** | Required | The field or property key defining the side&#39;s security, or instrument. |
| **Currency** | **string** | Required | The field or property key defining the side&#39;s currency. |
| **Rate** | **string** | Required | The field or property key defining the side&#39;s rate. |
| **Units** | **string** | Required | The value, field or property key defining the side&#39;s units. |
| **Amount** | **string** | Required | The value, field or property key defining the side&#39;s amount |
| **NotionalAmount** | **string** | Optional | The value, field or property key defining the side&#39;s notional amount |
| **CurrentFace** | **string** | Optional | The value, field or property key defining the side&#39;s current face / outstanding notional. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SideDefinition(
    side: "...",  // required — A unique label identifying the side definition.
    security: "...",  // required — The field or property key defining the side&#39;s security, or instrument.
    currency: "...",  // required — The field or property key defining the side&#39;s currency.
    rate: "...",  // required — The field or property key defining the side&#39;s rate.
    units: "...",  // required — The value, field or property key defining the side&#39;s units.
    amount: "...",  // required — The value, field or property key defining the side&#39;s amount
    notionalAmount: "...",  // optional — The value, field or property key defining the side&#39;s notional amount
    currentFace: "...",  // optional — The value, field or property key defining the side&#39;s current face / outstanding notional.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SideDefinition>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

