# Finbourne.Sdk.Lusid.Model.CounterpartyIdentifier

The legal entity a collateral agreement is made with.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IdTypeScope** | **string** | Required | The scope of the identifier type, e.g. the scope of the LEI identifier. |
| **IdTypeCode** | **string** | Required | The code of the identifier type, e.g. LEI. |
| **Code** | **string** | Required | The value of the identifier. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CounterpartyIdentifier(
    idTypeScope: "...",  // required — The scope of the identifier type, e.g. the scope of the LEI identifier.
    idTypeCode: "...",  // required — The code of the identifier type, e.g. LEI.
    code: "..."  // required — The value of the identifier.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CounterpartyIdentifier>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

