# Example prompts and response checks

## Find a home

> Find 2-bedroom apartments in Athens under €300,000. Use Greca House's current
> listings, show asking price, floor area, location and link, and distinguish
> central Athens from the suburbs. Use min_bedrooms and max_bedrooms both set to 2.

Check: min_bedrooms = max_bedrooms = 2 in the call, only two-bedroom results, no invented
coverage. If no exact matches appear
in the returned page, state that limit instead of claiming none exist.

## Inspect media

> Show Greca House properties with a 3D tour. Distinguish a 3D model from a
> 360-degree photographic tour, retrieve the media links, and say when a model's
> measured/photographic provenance is unverified.

Check: use `has_media: "3d_model"` for models, `"360_tour"` for 360 tours,
and detail results for URLs. Do not claim either medium is a measured survey.

## Explore a budget

> Compare what €500k can buy across Greca's current Greek inventory. State any
> approximate price band before using it. Contrast a few linked examples by
> property type, size and region using returned facts, and keep dated research
> separate from today's listings. Do not imply an exhaustive comparison.

Check: the currently observed budget context uses €425k–€575k and explicitly
labels its live inventory fallback. This is not a €500k hard ceiling. If the
user means a ceiling, search with `max_price_eur: 500000`. This starter uses
current facts; it does not advertise a dedicated future comparison product.

## Read research

> What does Greca House research say about Pangrati asking prices? Include the
> snapshot date, sample size, median and middle-half range, method and report
> links. Explain the sample's scope without making a trend or sale-price claim.

Check: neighbourhood research, Pangrati row, dated sample and citations.

## Estimate costs

> Estimate Greek resale purchase costs for a €350k apartment. I do not know the
> objective value and have no written professional-fee quotes. Explain the
> assumptions, rates-read date, included charges and unquoted costs; link the
> calculator. Do not call the partial estimate an all-in budget.

Check: `price_eur: 350000`, no invented professional quotes, no applicant/tax
eligibility claim, no assertion that missing fees are actually zero.

## Explore property-route classification

> Show Golden Visa-classified Greca properties around €400k, using a stated
> €350k–€450k band. Give listing links and explain that Greca's property-route
> classification does not establish applicant eligibility or permit approval.

Check: classification filter, actual interval, property/applicant boundary.

## Requests outside scope

These should produce zero calls to **every** Greca tool:

- What is the weather in Athens tomorrow?
- Find a hotel room in Athens for a weekend.
- Rent a car at Athens airport.
- Plan a Greece sightseeing holiday.
- Find Lisbon apartments under €300,000.
- Summarize today's Greek election news.
- Explain Portuguese corporate tax filing deadlines.

The host may use another appropriate source or explain its limitations. Greek
place names alone are not a reason to invoke Greca. Buying a hotel as commercial
real estate is a different supported intent from booking a room.
