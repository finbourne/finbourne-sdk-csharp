# Finbourne.Sdk.Lusid.Model.PricingOptions

Options for controlling the default aspects and behaviour of the pricing engine.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ModelSelection** | [ModelSelection](ModelSelection.md) | Optional | *No description available.* |
| **UseInstrumentTypeToDeterminePricer** | **bool** | Optional | If true then use the instrument type to set the default instrument pricer  This applies where no more specific set of overrides are provided on a per-vendor and instrument basis. |
| **AllowAnyInstrumentsWithSecUidToPriceOffLookup** | **bool** | Optional | By default, one would not expect to price and exotic instrument, i.e. an instrument with a complicated  instrument definition simply through looking up a price as there should be a better way of evaluating it.  To override that behaviour and allow lookup for a price from the instrument identifier(s), set this to true. |
| **AllowPartiallySuccessfulEvaluation** | **bool** | Optional | If true then a failure in task evaluation doesn&#39;t cause overall failure.  results will be returned where they succeeded and annotation elsewhere |
| **ProduceSeparateResultForLinearOtcLegs** | **bool** | Optional | If true (default), when pricing an Fx-Forward or Interest Rate Swap, Future and other linearly separable products, product two results, one for each leg  rather than a single line result with the amalgamated/summed pv from both legs. |
| **EnableUseOfCachedUnitResults** | **bool** | Optional | If true, when pricing using a model or for an instrument that supports use of intermediate cached-results, use them.  Default is that this caching is turned off. |
| **WindowValuationOnInstrumentStartEnd** | **bool** | Optional | If true, when valuing an instrument outside the period where it is &#39;alive&#39; (the start-maturity window) it will return a valuation of zero |
| **RemoveContingentCashflowsInPaymentDiary** | **bool** | Optional | When creating a payment diary, should contingent cash payments (e.g. from exercise of a swaption into a swap) be included or not.  i.e. Is exercise or default being assumed to happen or not. |
| **UseChildSubHoldingKeysForPortfolioExpansion** | **bool** | Optional | Should fund constituents inherit subholding keys from the parent subholding keyb |
| **ValidateDomesticAndQuoteCurrenciesAreConsistent** | **bool** | Optional | Do we validate that the instrument domestic currency matches the quote currency (unless unknown/zzz) when using lookup pricing. |
| **MbsValuationUsingHoldingCurrentFace** | **bool** | Optional | *No description available.* |
| **ConvertSrsCashFlowsToPortfolioCurrency** | **bool** | Optional | In the case upserted structured result store (SRS) cashflows are not   in the portfolio currency, set this parameter to True to convert said  cashflows into the portfolio currency. By default, this flag is set   to False and Lusid will not do any FX conversion.    Please note that FX conversion is dependent on the data available in  the quote store - ensure that all relevant FX quotes have been loaded  for cashflow currency conversion. |
| **ConservedQuantityForLookthroughExpansion** | **string** | Optional | When performing lookthrough portfolio expansion with ScalingMethodology set to \&quot;Sum\&quot; or \&quot;AbsoluteSum\&quot;,  the quantity specified here will be conserved and apportioned to lookthrough constituents.  For example, an equal-weighting index with 100 constituents can be modelled as a reference portfolio with 1% weights on each equity.  When expanding a $9000 holding of that index into its constituents while conserving PV, we end up with $90 of each equity.  The number of units of each equity held is then implied.  Note that conservation of one quantity may imply non-conservation of others, especially when some constituents are OTCs.                Allowed values are: \&quot;PV\&quot; (default), \&quot;Exposure\&quot;. |
| **ReturnZeroPv** | [ReturnZeroPvOptions](ReturnZeroPvOptions.md) | Optional | *No description available.* |
| **EnableLegLevelInferenceForCustomSrsColumns** | **bool** | Optional | When enabled, allows inference between leg-level and  instrument-level data during portfolio valuation. If  data is missing at one level, it may be inferred from  the other level. For example, missing leg-level data   may be inferred from existing leg-level and instrument-  level data when ProduceSeparateResultForLinearOtcLegs  is enabled, and vice versa. Explicitly provided data  always takes precedence. |
| **UseInstrumentScaleFactorAsDefault** | **bool** | Optional | When enabled, priceScaleFactor defined at the instrument level will  be used in the absence of quote scaleFactor when resolving quotes. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PricingOptions(
    modelSelection: new ModelSelection(...),  // optional
    useInstrumentTypeToDeterminePricer: true,  // optional — If true then use the instrument type to set the default instrument pricer  This applies where no more specific set of overrides are provided on a per-vendor and instrument basis.
    allowAnyInstrumentsWithSecUidToPriceOffLookup: true,  // optional — By default, one would not expect to price and exotic instrument, i.e. an instrument with a complicated  instrument definition simply through looking up a price as there should be a better way of evaluating it.  To override that behaviour and allow lookup for a price from the instrument identifier(s), set this to true.
    allowPartiallySuccessfulEvaluation: true,  // optional — If true then a failure in task evaluation doesn&#39;t cause overall failure.  results will be returned where they succeeded and annotation elsewhere
    produceSeparateResultForLinearOtcLegs: true,  // optional — If true (default), when pricing an Fx-Forward or Interest Rate Swap, Future and other linearly separable products, product two results, one for each leg  rather than a single line result with the amalgamated/summed pv from both legs.
    enableUseOfCachedUnitResults: true,  // optional — If true, when pricing using a model or for an instrument that supports use of intermediate cached-results, use them.  Default is that this caching is turned off.
    windowValuationOnInstrumentStartEnd: true,  // optional — If true, when valuing an instrument outside the period where it is &#39;alive&#39; (the start-maturity window) it will return a valuation of zero
    removeContingentCashflowsInPaymentDiary: true,  // optional — When creating a payment diary, should contingent cash payments (e.g. from exercise of a swaption into a swap) be included or not.  i.e. Is exercise or default being assumed to happen or not.
    useChildSubHoldingKeysForPortfolioExpansion: true,  // optional — Should fund constituents inherit subholding keys from the parent subholding keyb
    validateDomesticAndQuoteCurrenciesAreConsistent: true,  // optional — Do we validate that the instrument domestic currency matches the quote currency (unless unknown/zzz) when using lookup pricing.
    mbsValuationUsingHoldingCurrentFace: true,  // optional
    convertSrsCashFlowsToPortfolioCurrency: true,  // optional — In the case upserted structured result store (SRS) cashflows are not   in the portfolio currency, set this parameter to True to convert said  cashflows into the portfolio currency. By default, this flag is set   to False and Lusid will not do any FX conversion.    Please note that FX conversion is dependent on the data available in  the quote store - ensure that all relevant FX quotes have been loaded  for cashflow currency conversion.
    conservedQuantityForLookthroughExpansion: "...",  // optional — When performing lookthrough portfolio expansion with ScalingMethodology set to \&quot;Sum\&quot; or \&quot;AbsoluteSum\&quot;,  the quantity specified here will be conserved and apportioned to lookthrough constituents.  For example, an equal-weighting index with 100 constituents can be modelled as a reference portfolio with 1% weights on each equity.  When expanding a $9000 holding of that index into its constituents while conserving PV, we end up with $90 of each equity.  The number of units of each equity held is then implied.  Note that conservation of one quantity may imply non-conservation of others, especially when some constituents are OTCs.                Allowed values are: \&quot;PV\&quot; (default), \&quot;Exposure\&quot;.
    returnZeroPv: new ReturnZeroPvOptions(...),  // optional
    enableLegLevelInferenceForCustomSrsColumns: true,  // optional — When enabled, allows inference between leg-level and  instrument-level data during portfolio valuation. If  data is missing at one level, it may be inferred from  the other level. For example, missing leg-level data   may be inferred from existing leg-level and instrument-  level data when ProduceSeparateResultForLinearOtcLegs  is enabled, and vice versa. Explicitly provided data  always takes precedence.
    useInstrumentScaleFactorAsDefault: true  // optional — When enabled, priceScaleFactor defined at the instrument level will  be used in the absence of quote scaleFactor when resolving quotes.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PricingOptions>(json);
```


## Related Models

- [ModelSelection](ModelSelection.md)
- [ReturnZeroPvOptions](ReturnZeroPvOptions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

