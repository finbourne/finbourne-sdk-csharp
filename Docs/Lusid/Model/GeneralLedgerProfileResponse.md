# Finbourne.Sdk.Lusid.Model.GeneralLedgerProfileResponse

A General Ledger Profile Definition.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **ChartOfAccountsId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **GeneralLedgerProfileCode** | **string** | Required | The unique code for the General Ledger Profile |
| **DisplayName** | **string** | Required | The name of the General Ledger Profile |
| **Description** | **string** | Optional | A description for the General Ledger Profile |
| **GeneralLedgerProfileMappings** | [List&lt;GeneralLedgerProfileMapping&gt;](GeneralLedgerProfileMapping.md) | Required | Rules for mapping Account or property values to aggregation pattern definitions |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GeneralLedgerProfileResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    chartOfAccountsId: new ResourceId(...),  // required
    generalLedgerProfileCode: "...",  // required — The unique code for the General Ledger Profile
    displayName: "...",  // required — The name of the General Ledger Profile
    description: "...",  // optional — A description for the General Ledger Profile
    generalLedgerProfileMappings: new List<GeneralLedgerProfileMapping>(),  // required — Rules for mapping Account or property values to aggregation pattern definitions
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GeneralLedgerProfileResponse>(json);
```

- [ResourceId](ResourceId.md)
- [GeneralLedgerProfileMapping](GeneralLedgerProfileMapping.md) — used in `GeneralLedgerProfileMappings`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

