# Finbourne.Sdk.Lusid.Model.SecurityElection

Security election for Events that result in equity
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ElectionKey** | **string** | Required | Unique key associated to this election. |
| **IsChosen** | **bool** | Optional | Is this the election that has been explicitly chosen from multiple options. |
| **IsDefault** | **bool** | Optional | Is this election automatically applied in the absence of an election having been made.  May only be true for one election if multiple are provided. |
| **Price** | **decimal?** | Optional | Price per unit of the security. At least one of UnitsRatio or Price must be provided.  Price must non-zero. |
| **UnitsRatio** | [UnitsRatio](UnitsRatio.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SecurityElection(
    electionKey: "...",  // required — Unique key associated to this election.
    isChosen: true,  // optional — Is this the election that has been explicitly chosen from multiple options.
    isDefault: true,  // optional — Is this election automatically applied in the absence of an election having been made.  May only be true for one election if multiple are provided.
    price: 0.0d,  // optional — Price per unit of the security. At least one of UnitsRatio or Price must be provided.  Price must non-zero.
    unitsRatio: new UnitsRatio(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SecurityElection>(json);
```

- [UnitsRatio](UnitsRatio.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

