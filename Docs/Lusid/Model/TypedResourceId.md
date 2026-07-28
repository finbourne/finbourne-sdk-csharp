# Finbourne.Sdk.Lusid.Model.TypedResourceId

Represents the user-defined identifier for a Legal Entity.  Users can define their own, scoped identifiers for Legal Entities using identifier properties.  For example,  when used to identify a Legal Entity, the identifier defined by LegalEntity/myScope/1234ABC0000000000063 would be represented as   {     \"idTypeScope\": \"myScope\",     \"idTypeCode\": \"1234ABC0000000000063\",     \"code\": \"ACME_CO\"   }
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IdTypeScope** | **string** | Required | The scope of the identifier&#39;s (property) definition. |
| **IdTypeCode** | **string** | Required | The code of identifier&#39;s (property) definition. This describes what the identifier represents.  For a Legal Entity, this might be a registeredCompanyNumber or LEI. |
| **Code** | **string** | Required | The value of the user-defined identifier in respect of the entity. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TypedResourceId(
    idTypeScope: "...",  // required — The scope of the identifier&#39;s (property) definition.
    idTypeCode: "...",  // required — The code of identifier&#39;s (property) definition. This describes what the identifier represents.  For a Legal Entity, this might be a registeredCompanyNumber or LEI.
    code: "..."  // required — The value of the user-defined identifier in respect of the entity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TypedResourceId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

