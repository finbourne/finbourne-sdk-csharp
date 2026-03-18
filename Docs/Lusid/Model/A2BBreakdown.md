# Finbourne.Sdk.Lusid.Model.A2BBreakdown

A2B Breakdown - Shows the total, and each sub-element within an A2B Category
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Total** | **decimal** | Optional | The total value of all the components within this category. |
| **Currency** | **string** | Optional | The currency. Applies to the Total, as well as all the componenents. |
| **Components** | **Dictionary&lt;string, decimal&gt;** | Optional | The individual components that make up the category. For example, the Start category may have Cost, Unrealised gains and accrued interest components. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new A2BBreakdown(
    total: 0.0d,  // optional — The total value of all the components within this category.
    currency: "...",  // optional — The currency. Applies to the Total, as well as all the componenents.
    components:   // optional — The individual components that make up the category. For example, the Start category may have Cost, Unrealised gains and accrued interest components.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<A2BBreakdown>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

