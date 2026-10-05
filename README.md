# Greca House: Greek Property (Gemini CLI extension)

Connect Gemini CLI to the public Greca House MCP server at
[grecahouse.com/mcp](https://grecahouse.com/mcp). Search Greca House's current
property listings in Greece, open a listing, read its dated asking-price
research, and estimate the costs of buying a resale property in Greece.
Greca House is an independent real-estate brokerage in central Athens.

Results cover Greca House's own public listings, not the whole Greek market,
and prices are asking prices. A Golden Visa classification is Greca House's
classification of the property route: it does not decide an applicant's
eligibility and is not legal advice. Google has not endorsed this extension.

## Install

Gemini CLI with its normal model sign-in is all you need. The extension asks
for no Greca House account, key or OAuth.

```
gemini extensions install https://github.com/grecahouse/greca-house-gemini-cli-extension
```

Restart Gemini CLI, then run `/mcp`: the server `greca_house` should be listed
as connected, with five tools.

| Tool | What it does |
| --- | --- |
| `search_greece_properties` | Current listings by area, region, sale or rent, type, price, bedrooms (exact or range), size, media and Golden Visa classification |
| `get_property_details` | One listing by its GH reference: description, facts, features, media links, page URL |
| `compare_budget_by_area` | Dated asking-price research by area, and what a budget is listed for |
| `get_greece_market_research` | The research reports, method and CSV downloads |
| `estimate_greece_buying_costs` | Transfer tax, municipal surcharge, Cadastre and notary fee; professional fees only from your quotes |

All five tools are read-only. They create no enquiry and store no request.

## Try

- Find 2-bedroom apartments in Athens under €300,000.
- Show Greca House properties with a 3D model; tell 3D models from 360° tours.
- What does Greca House research say about Pangrati asking prices?
- Estimate Greek resale purchase costs for a €350k apartment.
- Show Golden Visa-classified Greca properties between €350k and €450k.

More prompts and what a good answer contains: [examples.md](examples.md).
Routing fixtures used for testing: [routing-matrix.json](routing-matrix.json).

## Update and uninstall

```
gemini extensions update greca-house
gemini extensions uninstall greca-house
```

## Data handling

See [PRIVACY.md](PRIVACY.md) and [SECURITY.md](SECURITY.md), and Greca House's
privacy policy: https://grecahouse.com/en/privacy-policy

Support: https://grecahouse.com/en/contact

Licence: MIT.
