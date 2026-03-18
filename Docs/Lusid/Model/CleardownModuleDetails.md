# Finbourne.Sdk.Lusid.Model.CleardownModuleDetails

A Cleardown Module request definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the Cleardown Module. |
| **Description** | **string** | Optional | A description for the Cleardown Module. |
| **Status** | **string** | Required | The Cleardown Module status. Can be Active or Inactive. Defaults to Active. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CleardownModuleDetails(
    displayName: "...",  // required — The name of the Cleardown Module.
    description: "...",  // optional — A description for the Cleardown Module.
    status: "..."  // required — The Cleardown Module status. Can be Active or Inactive. Defaults to Active.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CleardownModuleDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

