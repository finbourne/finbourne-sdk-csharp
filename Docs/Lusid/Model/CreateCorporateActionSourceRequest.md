# Finbourne.Sdk.Lusid.Model.CreateCorporateActionSourceRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope of the corporate action source |
| **Code** | **string** | Required | The code of the corporate action source |
| **DisplayName** | **string** | Required | The name of the corporate action source |
| **Description** | **string** | Optional | The description of the corporate action source |
| **InstrumentScopes** | **List&lt;string&gt;** | Optional | The list of instrument scopes used as the scope resolution strategy when resolving instruments of upserted corporate actions. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateCorporateActionSourceRequest(
    scope: "...",  // required — The scope of the corporate action source
    code: "...",  // required — The code of the corporate action source
    displayName: "...",  // required — The name of the corporate action source
    description: "...",  // optional — The description of the corporate action source
    instrumentScopes:   // optional — The list of instrument scopes used as the scope resolution strategy when resolving instruments of upserted corporate actions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateCorporateActionSourceRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

