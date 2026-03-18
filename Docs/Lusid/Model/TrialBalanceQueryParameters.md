# Finbourne.Sdk.Lusid.Model.TrialBalanceQueryParameters

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Start** | [DateOrDiaryEntry](DateOrDiaryEntry.md) | Optional | *No description available.* |
| **End** | [DateOrDiaryEntry](DateOrDiaryEntry.md) | Optional | *No description available.* |
| **DateMode** | **string** | Optional | The mode of calculation of the trial balance. The available values are: ActivityDate, AccountingDate. |
| **GeneralLedgerProfileCode** | **string** | Optional | The optional code of a general ledger profile used to decorate trial balance with levels. |
| **PropertyKeys** | **List&lt;string&gt;** | Optional | A list of property keys from the &#39;Account&#39; domain to decorate onto the trial balance. |
| **ExcludeCleardownModule** | **bool** | Optional | By deafult this flag is set to false, if this is set to true, no cleardown module will be applied to the trial balance. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TrialBalanceQueryParameters(
    start: new DateOrDiaryEntry(...),  // optional
    end: new DateOrDiaryEntry(...),  // optional
    dateMode: "...",  // optional — The mode of calculation of the trial balance. The available values are: ActivityDate, AccountingDate.
    generalLedgerProfileCode: "...",  // optional — The optional code of a general ledger profile used to decorate trial balance with levels.
    propertyKeys: ,  // optional — A list of property keys from the &#39;Account&#39; domain to decorate onto the trial balance.
    excludeCleardownModule: true  // optional — By deafult this flag is set to false, if this is set to true, no cleardown module will be applied to the trial balance.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TrialBalanceQueryParameters>(json);
```


## Related Models

- [DateOrDiaryEntry](DateOrDiaryEntry.md)
- [DateOrDiaryEntry](DateOrDiaryEntry.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

