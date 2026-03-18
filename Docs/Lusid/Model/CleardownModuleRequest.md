# Finbourne.Sdk.Lusid.Model.CleardownModuleRequest

A Cleardown Module request definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the Cleardown Module. |
| **DisplayName** | **string** | Required | The name of the Cleardown Module. |
| **Description** | **string** | Optional | A description for the Cleardown Module. |
| **Rules** | [List&lt;CleardownModuleRule&gt;](CleardownModuleRule.md) | Optional | The Cleardown Rules that apply for the Cleardown Module. Rules are evaluated in the order they occur in this collection. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CleardownModuleRequest(
    code: "...",  // required — The code of the Cleardown Module.
    displayName: "...",  // required — The name of the Cleardown Module.
    description: "...",  // optional — A description for the Cleardown Module.
    rules: new List<CleardownModuleRule>()  // optional — The Cleardown Rules that apply for the Cleardown Module. Rules are evaluated in the order they occur in this collection.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CleardownModuleRequest>(json);
```

- [CleardownModuleRule](CleardownModuleRule.md) — used in `Rules`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

