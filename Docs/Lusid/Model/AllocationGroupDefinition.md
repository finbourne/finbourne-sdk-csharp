# Finbourne.Sdk.Lusid.Model.AllocationGroupDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Classes** | [List&lt;AllocationGroupClassDefinition&gt;](AllocationGroupClassDefinition.md) | Optional | An optional list of share classes that belong to this group. Each entry must reference a ShareClass already present on the Fund. You can provide this or the Formula, but not both. |
| **Code** | **string** | Required | The unique code for the Allocation Group. Must be unique within the Fund. |
| **Name** | **string** | Required | The display name of the Allocation Group. |
| **Description** | **string** | Optional | An optional description for the Allocation Group. |
| **ShareClassShortCode** | **string** | Required | The short code that identifies the Allocation Group. |
| **ApportionmentMethodProperty** | [AllocationMethodProperty](AllocationMethodProperty.md) | Optional | *No description available.* |
| **Formula** | **string** | Optional | An optional filter expression used to define which classes belong to this group, based on fund grouping criteria. You can provide this or the Classes, but not both. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationGroupDefinition(
    classes: new List<AllocationGroupClassDefinition>(),  // optional — An optional list of share classes that belong to this group. Each entry must reference a ShareClass already present on the Fund. You can provide this or the Formula, but not both.
    code: "...",  // required — The unique code for the Allocation Group. Must be unique within the Fund.
    name: "...",  // required — The display name of the Allocation Group.
    description: "...",  // optional — An optional description for the Allocation Group.
    shareClassShortCode: "...",  // required — The short code that identifies the Allocation Group.
    apportionmentMethodProperty: new AllocationMethodProperty(...),  // optional
    formula: "..."  // optional — An optional filter expression used to define which classes belong to this group, based on fund grouping criteria. You can provide this or the Classes, but not both.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationGroupDefinition>(json);
```


## Related Models

- [AllocationGroupClassDefinition](AllocationGroupClassDefinition.md) — used in `Classes`
- [AllocationMethodProperty](AllocationMethodProperty.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

