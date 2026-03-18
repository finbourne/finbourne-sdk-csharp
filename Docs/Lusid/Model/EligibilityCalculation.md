# Finbourne.Sdk.Lusid.Model.EligibilityCalculation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntitlementDate** | **string** | Required | *No description available.* |
| **EligibleUnits** | **string** | Required | *No description available.* |
| **DateModifiableByInstruction** | **bool** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EligibilityCalculation(
    entitlementDate: "...",  // required
    eligibleUnits: "...",  // required
    dateModifiableByInstruction: true  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EligibilityCalculation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

