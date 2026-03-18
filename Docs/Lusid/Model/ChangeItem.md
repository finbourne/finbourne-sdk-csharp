# Finbourne.Sdk.Lusid.Model.ChangeItem

Information about a change to a field / property.  At least one of 'PreviousValue' or 'NewValue' will be set.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FieldName** | **string** | Required | The name of the field or property that has been changed. |
| **PreviousValue** | **string** | Optional | The previous value for this field / property. |
| **NewValue** | **string** | Optional | The new value for this field / property. |
| **EffectiveFrom** | **DateTimeOffset?** | Optional | The market data time, i.e. the time to run the change from. |
| **EffectiveUntil** | **DateTimeOffset?** | Optional | The market data time, i.e. the time to run the change until. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ChangeItem(
    fieldName: "...",  // required — The name of the field or property that has been changed.
    previousValue: "...",  // optional — The previous value for this field / property.
    newValue: "...",  // optional — The new value for this field / property.
    effectiveFrom: DateTimeOffset.Now,  // optional — The market data time, i.e. the time to run the change from.
    effectiveUntil: DateTimeOffset.Now  // optional — The market data time, i.e. the time to run the change until.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ChangeItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

