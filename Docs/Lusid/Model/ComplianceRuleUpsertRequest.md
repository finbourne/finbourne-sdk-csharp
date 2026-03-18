# Finbourne.Sdk.Lusid.Model.ComplianceRuleUpsertRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | *No description available.* |
| **Code** | **string** | Optional | *No description available.* |
| **DisplayName** | **string** | Optional | *No description available.* |
| **Type** | **string** | Required | *No description available.* |
| **PropertyKey** | **string** | Optional | *No description available.* |
| **Value** | **string** | Optional | *No description available.* |
| **LowerBound** | **decimal** | Required | *No description available.* |
| **UpperBound** | **decimal** | Required | *No description available.* |
| **Schedule** | **string** | Required | *No description available.* |
| **HardRequirement** | **bool** | Required | *No description available.* |
| **TargetPortfolioIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **AddressKey** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleUpsertRequest(
    scope: "...",  // required
    code: "...",  // optional
    displayName: "...",  // optional
    type: "...",  // required
    propertyKey: "...",  // optional
    value: "...",  // optional
    lowerBound: 0.0d,  // required
    upperBound: 0.0d,  // required
    schedule: "...",  // required
    hardRequirement: true,  // required
    targetPortfolioIds: new List<ResourceId>(),  // required
    description: "...",  // optional
    addressKey: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleUpsertRequest>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

