# Finbourne.Sdk.Lusid.Model.PropertyKeyComplianceParameter

> **Inherits from:** [ComplianceParameter](ComplianceParameter.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Required | The key that uniquely identifies the property. It has the format {domain}/{scope}/{code}. |
| **ComplianceParameterType** | **string** | Required | The parameter type. The available values are: BoolComplianceParameter, StringComplianceParameter, DecimalComplianceParameter, DateTimeComplianceParameter, PropertyKeyComplianceParameter, AddressKeyComplianceParameter, PortfolioIdComplianceParameter, PortfolioGroupIdComplianceParameter, StringListComplianceParameter, BoolListComplianceParameter, DateTimeListComplianceParameter, DecimalListComplianceParameter, PropertyKeyListComplianceParameter, AddressKeyListComplianceParameter, PortfolioIdListComplianceParameter, PortfolioGroupIdListComplianceParameter, InstrumentListComplianceParameter, FilterPredicateComplianceParameter, GroupFilterPredicateComplianceParameter, GroupBySelectorComplianceParameter, PropertyListComplianceParameter, GroupCalculationComplianceParameter Default: `ComplianceParameterTypeEnum.PropertyKeyComplianceParameter` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PropertyKeyComplianceParameter(
    value: "...",  // required — The key that uniquely identifies the property. It has the format {domain}/{scope}/{code}.
    complianceParameterType: "..."  // required — The parameter type. The available values are: BoolComplianceParameter, StringComplianceParameter, DecimalComplianceParameter, DateTimeComplianceParameter, PropertyKeyComplianceParameter, AddressKeyComplianceParameter, PortfolioIdComplianceParameter, PortfolioGroupIdComplianceParameter, StringListComplianceParameter, BoolListComplianceParameter, DateTimeListComplianceParameter, DecimalListComplianceParameter, PropertyKeyListComplianceParameter, AddressKeyListComplianceParameter, PortfolioIdListComplianceParameter, PortfolioGroupIdListComplianceParameter, InstrumentListComplianceParameter, FilterPredicateComplianceParameter, GroupFilterPredicateComplianceParameter, GroupBySelectorComplianceParameter, PropertyListComplianceParameter, GroupCalculationComplianceParameter
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PropertyKeyComplianceParameter>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

