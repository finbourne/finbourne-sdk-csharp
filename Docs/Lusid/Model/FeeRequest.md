# Finbourne.Sdk.Lusid.Model.FeeRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the Fee. |
| **FeeTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | The name of the Fee. |
| **Description** | **string** | Optional | A description for the Fee. |
| **Origin** | **string** | Optional | The origin or source of the Fee accrual. |
| **CalculationBase** | **string** | Optional | The calculation base for a Fee that is calculated using a percentage (TotalAnnualAccrualAmount and CalculationBase cannot both be present). When the Fee is a ShareClass Fee (i.e: when ShareClasses contains at least one value), each of the following would be a valid CalculationBase: \&quot;10000.00\&quot;, \&quot;ShareClass.GAV\&quot;, \&quot;ShareClass.GAV - ShareClass.Fees[ShareClassFeeCode1].Amount\&quot;, \&quot;ShareClass.Fees[ShareClassFeeCode1].CalculationBase\&quot;. When the Fee is a NonShareClassSpecific Fee (i.e: when ShareClasses contains no values), each of the following would be a valid CalculationBase: \&quot;10000.00\&quot;, \&quot;GAV\&quot;, \&quot;GAV - Fees[NonClassSpecificFeeCode1].Amount\&quot;, \&quot;Fees[NonClassSpecificFeeCode1].CalculationBase\&quot;.  |
| **AccrualCurrency** | **string** | Required | The accrual currency. |
| **Treatment** | **string** | Required | The accrual period of the Fee; &#39;Monthly&#39; or &#39;Daily&#39;. |
| **TotalAnnualAccrualAmount** | **decimal?** | Optional | The total annual accrued amount for the Fee. (TotalAnnualAccrualAmount and CalculationBase cannot both be present) |
| **FeeRatePercentage** | **decimal?** | Optional | The fee rate percentage. (Required when CalculationBase is present and not compatible with TotalAnnualAccrualAmount) |
| **PayableFrequency** | **string** | Required | The payable frequency for the Fee; &#39;Annually&#39;, &#39;Quarterly&#39; or &#39;Monthly&#39;. |
| **BusinessDayConvention** | **string** | Required | The business day convention to use for Fee calculations on weekends or holidays. Supported string values are: [Previous, P, Following, F, None]. |
| **StartDate** | **DateTimeOffset** | Required | The start date of the Fee. |
| **EndDate** | **DateTimeOffset?** | Optional | The end date of the Fee. |
| **AnchorDate** | [DayMonth](DayMonth.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The Fee properties. These will be from the &#39;Fee&#39; domain. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **ShareClasses** | **List&lt;string&gt;** | Optional | The short codes of the ShareClasses that the Fee should be applied to. Optional: if this is null or empty, then the Fee will be divided between all the ShareClasses of the Fund according to the capital ratio. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeRequest(
    code: "...",  // required — The code of the Fee.
    feeTypeId: new ResourceId(...),  // required
    displayName: "...",  // required — The name of the Fee.
    description: "...",  // optional — A description for the Fee.
    origin: "...",  // optional — The origin or source of the Fee accrual.
    calculationBase: "...",  // optional — The calculation base for a Fee that is calculated using a percentage (TotalAnnualAccrualAmount and CalculationBase cannot both be present). When the Fee is a ShareClass Fee (i.e: when ShareClasses contains at least one value), each of the following would be a valid CalculationBase: \&quot;10000.00\&quot;, \&quot;ShareClass.GAV\&quot;, \&quot;ShareClass.GAV - ShareClass.Fees[ShareClassFeeCode1].Amount\&quot;, \&quot;ShareClass.Fees[ShareClassFeeCode1].CalculationBase\&quot;. When the Fee is a NonShareClassSpecific Fee (i.e: when ShareClasses contains no values), each of the following would be a valid CalculationBase: \&quot;10000.00\&quot;, \&quot;GAV\&quot;, \&quot;GAV - Fees[NonClassSpecificFeeCode1].Amount\&quot;, \&quot;Fees[NonClassSpecificFeeCode1].CalculationBase\&quot;. 
    accrualCurrency: "...",  // required — The accrual currency.
    treatment: "...",  // required — The accrual period of the Fee; &#39;Monthly&#39; or &#39;Daily&#39;.
    totalAnnualAccrualAmount: 0.0d,  // optional — The total annual accrued amount for the Fee. (TotalAnnualAccrualAmount and CalculationBase cannot both be present)
    feeRatePercentage: 0.0d,  // optional — The fee rate percentage. (Required when CalculationBase is present and not compatible with TotalAnnualAccrualAmount)
    payableFrequency: "...",  // required — The payable frequency for the Fee; &#39;Annually&#39;, &#39;Quarterly&#39; or &#39;Monthly&#39;.
    businessDayConvention: "...",  // required — The business day convention to use for Fee calculations on weekends or holidays. Supported string values are: [Previous, P, Following, F, None].
    startDate: DateTimeOffset.Now,  // required — The start date of the Fee.
    endDate: DateTimeOffset.Now,  // optional — The end date of the Fee.
    anchorDate: new DayMonth(...),  // optional
    properties: new Property(...),  // optional — The Fee properties. These will be from the &#39;Fee&#39; domain.
    portfolioId: new ResourceId(...),  // optional
    shareClasses:   // optional — The short codes of the ShareClasses that the Fee should be applied to. Optional: if this is null or empty, then the Fee will be divided between all the ShareClasses of the Fund according to the capital ratio.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeeRequest>(json);
```

- [ResourceId](ResourceId.md)
- [DayMonth](DayMonth.md)
- [Property](Property.md) — used in `Properties`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

