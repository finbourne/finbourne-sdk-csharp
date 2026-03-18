# Finbourne.Sdk.Lusid.Model.SettlementConfigurationMethodOverride

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PropertyKey** | **string** | Required | Property Key to override the settlement method. Allowed values: &#39;Automatic&#39;, &#39;Instructed&#39; and &#39;Default&#39;, property key must be in the &#39;Transaction&#39; domain. For a derived property keys, the derivation formula should resolve one of the of the allowed values. &#39;Default&#39; will be treated the same as no or an invalid derived value, will fall back to use the regular settlement method. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementConfigurationMethodOverride(
    propertyKey: "..."  // required — Property Key to override the settlement method. Allowed values: &#39;Automatic&#39;, &#39;Instructed&#39; and &#39;Default&#39;, property key must be in the &#39;Transaction&#39; domain. For a derived property keys, the derivation formula should resolve one of the of the allowed values. &#39;Default&#39; will be treated the same as no or an invalid derived value, will fall back to use the regular settlement method.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementConfigurationMethodOverride>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

