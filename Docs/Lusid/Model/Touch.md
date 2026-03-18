# Finbourne.Sdk.Lusid.Model.Touch

Touch class for exotic FxOption
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Direction** | **string** | Required | Supported string (enumeration) values are: [Down, Up]. |
| **Level** | **decimal** | Required | Trigger level, which the underlying should (or should not) cross/touch. |
| **Monitoring** | **string** | Optional | Supported string (enumeration) values are: [European, Bermudan, American].  Defaults to \&quot;European\&quot; if not set. |
| **Type** | **string** | Required | Supported string (enumeration) values are: [Touch, Notouch]. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Touch(
    direction: "...",  // required — Supported string (enumeration) values are: [Down, Up].
    level: 0.0d,  // required — Trigger level, which the underlying should (or should not) cross/touch.
    monitoring: "...",  // optional — Supported string (enumeration) values are: [European, Bermudan, American].  Defaults to \&quot;European\&quot; if not set.
    type: "..."  // required — Supported string (enumeration) values are: [Touch, Notouch].
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Touch>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

