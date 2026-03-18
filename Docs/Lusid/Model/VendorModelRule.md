# Finbourne.Sdk.Lusid.Model.VendorModelRule

A rule that identifies the set of preferences to be used for a given library, model and instrument type.  There can be many such rules, though only the first found for a given combination would be used.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Supplier** | **string** | Required | The available values are: Lusid, RefinitivQps, RefinitivTracsWeb, VolMaster, IsdaCds, YieldBook, LusidCalc |
| **ModelName** | **string** | Required | The vendor library model name |
| **InstrumentType** | **string** | Required | The vendor library instrument type |
| **Parameters** | **string** | Optional | THIS FIELD IS DEPRECATED - use ModelOptions  The set of opaque model parameters, provided as a Json object, that is a string object which will internally be converted to a dictionary of string to object.  Note that this is not intended as the final form of this object. It will be replaced with a more structured object as the set of parameters that are possible is  better understood. |
| **ModelOptions** | [ModelOptions](ModelOptions.md) | Optional | *No description available.* |
| **InstrumentId** | **string** | Optional | This field should generally not be required. It indicates a specific case where there is a particular need to make a rule apply to only a single instrument  specified by an identifier on that instrument such as its LUID. One particular example would be to control the behaviour of a look-through portfolio scaling  methodology, such as where there is a mixture of indices and credit-debit portfolios where scaling on the sum of valuation would be deemed incorrectly for one  set but desired in general. |
| **AddressKeyFilters** | [List&lt;AddressKeyFilter&gt;](AddressKeyFilter.md) | Optional | Condition for model selection. If a condition is satisfied the default model for valuation is overridden (for that instrument). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VendorModelRule(
    supplier: "...",  // required — The available values are: Lusid, RefinitivQps, RefinitivTracsWeb, VolMaster, IsdaCds, YieldBook, LusidCalc
    modelName: "...",  // required — The vendor library model name
    instrumentType: "...",  // required — The vendor library instrument type
    parameters: "...",  // optional — THIS FIELD IS DEPRECATED - use ModelOptions  The set of opaque model parameters, provided as a Json object, that is a string object which will internally be converted to a dictionary of string to object.  Note that this is not intended as the final form of this object. It will be replaced with a more structured object as the set of parameters that are possible is  better understood.
    modelOptions: new ModelOptions(...),  // optional
    instrumentId: "...",  // optional — This field should generally not be required. It indicates a specific case where there is a particular need to make a rule apply to only a single instrument  specified by an identifier on that instrument such as its LUID. One particular example would be to control the behaviour of a look-through portfolio scaling  methodology, such as where there is a mixture of indices and credit-debit portfolios where scaling on the sum of valuation would be deemed incorrectly for one  set but desired in general.
    addressKeyFilters: new List<AddressKeyFilter>()  // optional — Condition for model selection. If a condition is satisfied the default model for valuation is overridden (for that instrument).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VendorModelRule>(json);
```

- [ModelOptions](ModelOptions.md)
- [AddressKeyFilter](AddressKeyFilter.md) — used in `AddressKeyFilters`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

