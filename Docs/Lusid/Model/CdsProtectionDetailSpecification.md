# Finbourne.Sdk.Lusid.Model.CdsProtectionDetailSpecification

CDSs generally conform to fairly standard definitions, but can be tweaked in a number of different ways.  This class gathers a number of common features which may deviate. These will default to the market standard when  no overrides are provided.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Seniority** | **string** | Optional | The seniority level of the CDS.  Supported string (enumeration) values are: [SNR, SUB, JRSUBUT2, PREFT1, SECDOM, SNRFOR, SUBLT2].  Defaults to \&quot;SUB\&quot; if not set. Default: `"SUB"` |
| **RestructuringType** | **string** | Optional | The restructuring clause.  Supported string (enumeration) values are: [CR, MR, MM, XR]. Defaults to \&quot;MM\&quot; if not set. Default: `"MM"` |
| **ProtectStartDay** | **bool** | Optional | Does the protection leg pay out in the case of default on the start date. Defaults to true if not set. Default: `true` |
| **PayAccruedInterestOnDefault** | **bool** | Optional | Should accrued interest on the premium leg be paid if a credit event occurs. Defaults to true if not set. Default: `true` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CdsProtectionDetailSpecification(
    seniority: "...",  // optional — The seniority level of the CDS.  Supported string (enumeration) values are: [SNR, SUB, JRSUBUT2, PREFT1, SECDOM, SNRFOR, SUBLT2].  Defaults to \&quot;SUB\&quot; if not set.
    restructuringType: "...",  // optional — The restructuring clause.  Supported string (enumeration) values are: [CR, MR, MM, XR]. Defaults to \&quot;MM\&quot; if not set.
    protectStartDay: true,  // optional — Does the protection leg pay out in the case of default on the start date. Defaults to true if not set.
    payAccruedInterestOnDefault: true  // optional — Should accrued interest on the premium leg be paid if a credit event occurs. Defaults to true if not set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CdsProtectionDetailSpecification>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

