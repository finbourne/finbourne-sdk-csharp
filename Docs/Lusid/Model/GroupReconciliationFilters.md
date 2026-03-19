# Finbourne.Sdk.Lusid.Model.GroupReconciliationFilters

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **string** | Optional | The filters for the left-side portfolio or portfolio group related data. |
| **Right** | **string** | Optional | The filters for the right-side portfolio or portfolio group related data. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationFilters(
    left: "...",  // optional — The filters for the left-side portfolio or portfolio group related data.
    right: "..."  // optional — The filters for the right-side portfolio or portfolio group related data.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationFilters>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

