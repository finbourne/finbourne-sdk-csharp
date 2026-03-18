# Finbourne.Sdk.Lusid.Model.StagingRuleApprovalCriteria

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RequiredApprovals** | **int?** | Optional | *No description available.* |
| **DecidingUser** | **string** | Optional | *No description available.* |
| **StagingUserCanDecide** | **bool?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagingRuleApprovalCriteria(
    requiredApprovals: 0,  // optional
    decidingUser: "...",  // optional
    stagingUserCanDecide: true  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagingRuleApprovalCriteria>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

