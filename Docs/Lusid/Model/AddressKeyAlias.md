# Finbourne.Sdk.Lusid.Model.AddressKeyAlias

An address key alias that maps a short alias key to a real key with options.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope of the alias |
| **Code** | **string** | Required | The code of the alias |
| **AliasKey** | **string** | Required | The alias address key, must start with \&quot;Alias/\&quot; prefix (e.g., \&quot;Alias/DailyNZPnL\&quot;) |
| **RealKey** | **string** | Required | The real address key this alias resolves to (e.g., \&quot;ProfitAndLoss/Total\&quot;). Must NOT start with \&quot;Alias/\&quot;. |
| **Options** | **Dictionary&lt;string, string&gt;** | Optional | Options to apply when resolving the alias (e.g., {\&quot;Window\&quot;:\&quot;Daily\&quot;,\&quot;TimeZone\&quot;:\&quot;NZ\&quot;}) |
| **DisplayName** | **string** | Optional | Human-readable display name |
| **Description** | **string** | Optional | Description of the alias |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AddressKeyAlias(
    scope: "...",  // required — The scope of the alias
    code: "...",  // required — The code of the alias
    aliasKey: "...",  // required — The alias address key, must start with \&quot;Alias/\&quot; prefix (e.g., \&quot;Alias/DailyNZPnL\&quot;)
    realKey: "...",  // required — The real address key this alias resolves to (e.g., \&quot;ProfitAndLoss/Total\&quot;). Must NOT start with \&quot;Alias/\&quot;.
    options: ,  // optional — Options to apply when resolving the alias (e.g., {\&quot;Window\&quot;:\&quot;Daily\&quot;,\&quot;TimeZone\&quot;:\&quot;NZ\&quot;})
    displayName: "...",  // optional — Human-readable display name
    description: "..."  // optional — Description of the alias
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AddressKeyAlias>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

