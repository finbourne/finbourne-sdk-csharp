# Finbourne.Sdk.Lusid.Model.MembershipAndStatus

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Required | Describes whether the entity is still a valid member of the data model. |
| **Scope** | **string** | Required | The scope of the unique identifier associated with the Custom Data Model. |
| **Code** | **string** | Required | The code of the unique identifier associated with the Custom Data Model. |
| **DisplayName** | **string** | Required | The name of the Custom Data Model. |
| **ValidationFailures** | **List&lt;string&gt;** | Required | A list of validation failures returned when the entity&#39;s status with respect to the current model is &#39;Invalid&#39; or &#39;Inadmissible&#39; |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MembershipAndStatus(
    status: "...",  // required — Describes whether the entity is still a valid member of the data model.
    scope: "...",  // required — The scope of the unique identifier associated with the Custom Data Model.
    code: "...",  // required — The code of the unique identifier associated with the Custom Data Model.
    displayName: "...",  // required — The name of the Custom Data Model.
    validationFailures:   // required — A list of validation failures returned when the entity&#39;s status with respect to the current model is &#39;Invalid&#39; or &#39;Inadmissible&#39;
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MembershipAndStatus>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

