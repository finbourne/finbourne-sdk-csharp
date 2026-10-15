# Finbourne.Sdk.Lusid.Model.PartnerStatementLineDifference

One figure that differs between two partner statements.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key of the figure. |
| **Before** | **decimal?** | Optional | The figure on the statement compared against. |
| **After** | **decimal?** | Optional | The figure on this statement. |
| **Change** | **decimal** | Required | After less before. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerStatementLineDifference(
    key: "...",  // required — The key of the figure.
    before: 0.0d,  // optional — The figure on the statement compared against.
    after: 0.0d,  // optional — The figure on this statement.
    change: 0.0d  // required — After less before.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerStatementLineDifference>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

