# Finbourne.Sdk.Lusid.Model.AggregationQuery

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AddressKey** | **string** | Required | The address that is the query to be made into the system. e.g. a Valuation/PV or Instrument/MaturityDate |
| **Description** | **string** | Required | What does the information that is being queried by the address mean. What is the address for. |
| **DisplayName** | **string** | Required | The suggested name that the user would wish to put on to the returned information for visualisation in preference to the address. |
| **Type** | **string** | Required | Financially meaningful results can be presented as either simple flat types or more complex expanded types. This field gives the type of the more complex representation.  For example, the present value (PV) of a holding could be represented either as a simple decimal (with currency implied) or as a decimal-currency pair. In this example, the type returned in this field would be \&quot;Result0D\&quot;, the decimal-currency pair. The available values are: String, Int, Decimal, DateTime, Boolean, ResultValue, Result0D, Json |
| **FlattenedType** | **string** | Required | Financially meaningful results can be presented as either simple flat types or more complex expanded types. This field gives the type of the simpler representation.  For example, the present value (PV) of a holding could be represented either as a simple decimal (with currency implied) or as a decimal-currency pair. In this example, the type returned in this field would be \&quot;Decimal\&quot;. The available values are: String, Int, Decimal, DateTime, Boolean, ResultValue, Result0D, Json |
| **ScalesWithHoldingQuantity** | **bool** | Required | Is the data scaled when it is for, e.g. a holding in an instrument. A key example would be the difference between price and PV. The present value of an instrument would scale with the quantity held. The price would be that for a hypothetical unit of that instrument, typically associated with the contract size. |
| **SupportedOperations** | **string** | Required | When performing an aggregation operation, what column type operations can be performed on the data. For example, it makes sense to sum decimals but not strings. Either can be counted. With more complex types, e.g. ResultValues, operations may be linked to a semantic meaning such as the currency of the result. In such cases the operations may be supported but context specific. For example, it makes sense to sum PVs in a single currency but not when the currency is different. In such cases, an error would result (it being assumed that no fx rates for currency conversion were implicit in the context). |
| **LifeCycleStatus** | **string** | Required | Within an API where an item can be accessed through an address or property, there is an associated status that determines whether the item is stable or likely to change. This status is one of [Experimental, Beta, EAP, Prod,  Deprecated]. If the item is deprecated it will be removed on or after the associated DateTime RemovalDate field. That field will not otherwise be set. |
| **RemovalDate** | **DateTimeOffset?** | Optional | If the life cycle status is set to deprecated then this will be populated with the date on or after which removal of the address query will happen |
| **ApplicableOptions** | [Dictionary&lt;string, AddressKeyOptionDefinition&gt;](AddressKeyOptionDefinition.md) | Optional | A mapping from option names to the definition that the corresponding option value must match. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregationQuery(
    addressKey: "...",  // required — The address that is the query to be made into the system. e.g. a Valuation/PV or Instrument/MaturityDate
    description: "...",  // required — What does the information that is being queried by the address mean. What is the address for.
    displayName: "...",  // required — The suggested name that the user would wish to put on to the returned information for visualisation in preference to the address.
    type: "...",  // required — Financially meaningful results can be presented as either simple flat types or more complex expanded types. This field gives the type of the more complex representation.  For example, the present value (PV) of a holding could be represented either as a simple decimal (with currency implied) or as a decimal-currency pair. In this example, the type returned in this field would be \&quot;Result0D\&quot;, the decimal-currency pair. The available values are: String, Int, Decimal, DateTime, Boolean, ResultValue, Result0D, Json
    flattenedType: "...",  // required — Financially meaningful results can be presented as either simple flat types or more complex expanded types. This field gives the type of the simpler representation.  For example, the present value (PV) of a holding could be represented either as a simple decimal (with currency implied) or as a decimal-currency pair. In this example, the type returned in this field would be \&quot;Decimal\&quot;. The available values are: String, Int, Decimal, DateTime, Boolean, ResultValue, Result0D, Json
    scalesWithHoldingQuantity: true,  // required — Is the data scaled when it is for, e.g. a holding in an instrument. A key example would be the difference between price and PV. The present value of an instrument would scale with the quantity held. The price would be that for a hypothetical unit of that instrument, typically associated with the contract size.
    supportedOperations: "...",  // required — When performing an aggregation operation, what column type operations can be performed on the data. For example, it makes sense to sum decimals but not strings. Either can be counted. With more complex types, e.g. ResultValues, operations may be linked to a semantic meaning such as the currency of the result. In such cases the operations may be supported but context specific. For example, it makes sense to sum PVs in a single currency but not when the currency is different. In such cases, an error would result (it being assumed that no fx rates for currency conversion were implicit in the context).
    lifeCycleStatus: "...",  // required — Within an API where an item can be accessed through an address or property, there is an associated status that determines whether the item is stable or likely to change. This status is one of [Experimental, Beta, EAP, Prod,  Deprecated]. If the item is deprecated it will be removed on or after the associated DateTime RemovalDate field. That field will not otherwise be set.
    removalDate: DateTimeOffset.Now,  // optional — If the life cycle status is set to deprecated then this will be populated with the date on or after which removal of the address query will happen
    applicableOptions: new AddressKeyOptionDefinition(...)  // optional — A mapping from option names to the definition that the corresponding option value must match.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregationQuery>(json);
```

- [AddressKeyOptionDefinition](AddressKeyOptionDefinition.md) — used in `ApplicableOptions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

