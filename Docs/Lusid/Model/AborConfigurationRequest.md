# Finbourne.Sdk.Lusid.Model.AborConfigurationRequest

The request used to create an AborConfiguration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code given for the Abor Configuration. |
| **DisplayName** | **string** | Optional | The name of the Abor Configuration. |
| **Description** | **string** | Optional | A description for the Abor Configuration. |
| **RecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ChartOfAccountsId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PostingModuleCodes** | **List&lt;string&gt;** | Optional | The Posting Module Codes from which the rules to be applied are retrieved. |
| **CleardownModuleCodes** | **List&lt;string&gt;** | Optional | The Cleardown Module Codes from which the rules to be applied are retrieved. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Abor Configuration. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AborConfigurationRequest(
    code: "...",  // required — The code given for the Abor Configuration.
    displayName: "...",  // optional — The name of the Abor Configuration.
    description: "...",  // optional — A description for the Abor Configuration.
    recipeId: new ResourceId(...),  // required
    chartOfAccountsId: new ResourceId(...),  // required
    postingModuleCodes: ,  // optional — The Posting Module Codes from which the rules to be applied are retrieved.
    cleardownModuleCodes: ,  // optional — The Cleardown Module Codes from which the rules to be applied are retrieved.
    properties: new Property(...)  // optional — A set of properties for the Abor Configuration.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AborConfigurationRequest>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

