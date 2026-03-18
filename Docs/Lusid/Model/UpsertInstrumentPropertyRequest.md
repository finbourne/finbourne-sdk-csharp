# Finbourne.Sdk.Lusid.Model.UpsertInstrumentPropertyRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IdentifierType** | **string** | Required | The unique identifier type to search for the instrument, for example &#39;Figi&#39;. |
| **Identifier** | **string** | Required | A value of that type to identify the instrument to upsert properties for, for example &#39;BBG000BLNNV0&#39;. |
| **Properties** | [List&lt;Property&gt;](Property.md) | Optional | A set of instrument properties and associated values to store for the instrument. Each property must be from the &#39;Instrument&#39; domain. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertInstrumentPropertyRequest(
    identifierType: "...",  // required — The unique identifier type to search for the instrument, for example &#39;Figi&#39;.
    identifier: "...",  // required — A value of that type to identify the instrument to upsert properties for, for example &#39;BBG000BLNNV0&#39;.
    properties: new List<Property>()  // optional — A set of instrument properties and associated values to store for the instrument. Each property must be from the &#39;Instrument&#39; domain.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertInstrumentPropertyRequest>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

