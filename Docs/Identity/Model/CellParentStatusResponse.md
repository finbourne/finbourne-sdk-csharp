# Finbourne.Sdk.Identity.Model.CellParentStatusResponse

Response containing the current cell parent status.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Optional | The current attachment status of the cell. |
| **AdminDomainName** | **string** | Optional | The name of the admin domain in the parent cell, if any. |
| **PrimaryDomainName** | **string** | Optional | The domain designated as the primary domain for this cell, if any. |
| **RegistrationStep** | **string** | Optional | The most recently reached registration checkpoint, or null if no registration has started. One of &#x60;UserEnsured&#x60;, &#x60;PATGenerated&#x60;, &#x60;PATPushed&#x60;. |
| **RegistrationError** | **string** | Optional | Operator-readable message describing the most recent registration failure, or null on success. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new CellParentStatusResponse(
    status: "...",  // optional — The current attachment status of the cell.
    adminDomainName: "...",  // optional — The name of the admin domain in the parent cell, if any.
    primaryDomainName: "...",  // optional — The domain designated as the primary domain for this cell, if any.
    registrationStep: "...",  // optional — The most recently reached registration checkpoint, or null if no registration has started. One of &#x60;UserEnsured&#x60;, &#x60;PATGenerated&#x60;, &#x60;PATPushed&#x60;.
    registrationError: "..."  // optional — Operator-readable message describing the most recent registration failure, or null on success.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CellParentStatusResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

