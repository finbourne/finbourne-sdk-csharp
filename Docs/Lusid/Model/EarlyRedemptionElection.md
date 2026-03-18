# Finbourne.Sdk.Lusid.Model.EarlyRedemptionElection

EarlyRedemptionElection for EarlyRedemptionEvent
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ElectionKey** | **string** | Required | Unique key associated to this election |
| **IsDefault** | **bool** | Optional | Is this election automatically applied in the absence of an election having been made.  May only be true for one election if multiple are provided. |
| **IsChosen** | **bool** | Optional | Is this the election that has been explicitly chosen from multiple options. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EarlyRedemptionElection(
    electionKey: "...",  // required — Unique key associated to this election
    isDefault: true,  // optional — Is this election automatically applied in the absence of an election having been made.  May only be true for one election if multiple are provided.
    isChosen: true  // optional — Is this the election that has been explicitly chosen from multiple options.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EarlyRedemptionElection>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

