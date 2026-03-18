# Finbourne.Sdk.Lusid.Model.DataType

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TypeValueRange** | **string** | Required | The available values are: Open, Closed |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **ValueType** | **string** | Required | The available values are: String, Int, Decimal, DateTime, Boolean, Map, List, PropertyArray, Percentage, Code, Id, Uri, CurrencyAndAmount, TradePrice, Currency, MetricValue, ResourceId, ResultValue, CutLocalTime, DateOrCutLabel, UnindexedText |
| **AcceptableValues** | **List&lt;string&gt;** | Optional | *No description available.* |
| **UnitSchema** | **string** | Optional | The available values are: NoUnits, Basic, Iso4217Currency |
| **AcceptableUnits** | [List&lt;IUnitDefinitionDto&gt;](IUnitDefinitionDto.md) | Optional | *No description available.* |
| **ReferenceData** | [ReferenceData](ReferenceData.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DataType(
    typeValueRange: "...",  // required — The available values are: Open, Closed
    id: new ResourceId(...),  // required
    displayName: "...",  // required
    description: "...",  // required
    valueType: "...",  // required — The available values are: String, Int, Decimal, DateTime, Boolean, Map, List, PropertyArray, Percentage, Code, Id, Uri, CurrencyAndAmount, TradePrice, Currency, MetricValue, ResourceId, ResultValue, CutLocalTime, DateOrCutLabel, UnindexedText
    acceptableValues: ,  // optional
    unitSchema: "...",  // optional — The available values are: NoUnits, Basic, Iso4217Currency
    acceptableUnits: new List<IUnitDefinitionDto>(),  // optional
    referenceData: new ReferenceData(...),  // optional
    varVersion: new ModelVersion(...),  // optional
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    stagedModifications: new StagedModificationsInfo(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DataType>(json);
```

- [ResourceId](ResourceId.md)
- [IUnitDefinitionDto](IUnitDefinitionDto.md)
- [ReferenceData](ReferenceData.md)
- [ModelVersion](ModelVersion.md)
- [StagedModificationsInfo](StagedModificationsInfo.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

