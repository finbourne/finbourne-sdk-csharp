# Finbourne.Sdk.Lusid.Model.BucketDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BucketId** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Required | *No description available.* |
| **FilterExpression** | **string** | Required | *No description available.* |
| **BucketType** | **string** | Required | Available values: Dealing, PnL, Fees, BalanceSheet, Misc. |
| **Unitised** | **bool?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketDefinition(
    bucketId: "...",  // required
    displayName: "...",  // required
    filterExpression: "...",  // required
    bucketType: "...",  // required — Available values: Dealing, PnL, Fees, BalanceSheet, Misc.
    unitised: true  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketDefinition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

