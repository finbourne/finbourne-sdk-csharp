# Finbourne.Sdk.Horizon.Model.InstanceIdentifier

Identifies a single instance of an integration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | Instance identifier. |
| **Warnings** | [List&lt;ValidationNoticeResponse&gt;](ValidationNoticeResponse.md) | Optional | Non-blocking findings about the saved configuration. Empty when there are none. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new InstanceIdentifier(
    id: "...",  // required — Instance identifier.
    warnings: new List<ValidationNoticeResponse>()  // optional — Non-blocking findings about the saved configuration. Empty when there are none.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstanceIdentifier>(json);
```

- [ValidationNoticeResponse](ValidationNoticeResponse.md) — used in `Warnings`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

