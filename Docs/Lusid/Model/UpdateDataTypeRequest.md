# Finbourne.Sdk.Lusid.Model.UpdateDataTypeRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Optional | The display name of the data type. |
| **Description** | **string** | Optional | The description of the data type. |
| **AcceptableValues** | **List&lt;string&gt;** | Optional | The acceptable set of values for this data type. Only applies to &#39;open&#39; value type range. |
| **AcceptableUnits** | [List&lt;UpdateUnitRequest&gt;](UpdateUnitRequest.md) | Optional | The definitions of the acceptable units. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateDataTypeRequest(
    displayName: "...",  // optional — The display name of the data type.
    description: "...",  // optional — The description of the data type.
    acceptableValues: ,  // optional — The acceptable set of values for this data type. Only applies to &#39;open&#39; value type range.
    acceptableUnits: new List<UpdateUnitRequest>()  // optional — The definitions of the acceptable units.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateDataTypeRequest>(json);
```

- [UpdateUnitRequest](UpdateUnitRequest.md) — used in `AcceptableUnits`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

