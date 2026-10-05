# Security and permissions

This extension adds one remote MCP connection. It includes no local shell command,
environment variables, credentials, OAuth configuration, settings prompt, hook,
skill executable or tool-confirmation bypass.

The live tools of server 1.1.0, inspected on 2026-10-04, are `search_greece_properties`,
`get_property_details`, `compare_budget_by_area`, `estimate_greece_buying_costs`
and `get_greece_market_research`. All advertise `readOnlyHint: true`,
`destructiveHint: false`, `openWorldHint: false` and `idempotentHint: true`. This confirms the advertised
surface; it is not an audit of the server's implementation or future changes.

Gemini CLI installation consent and its own policy engine still apply. Extension
MCP settings do not support `trust`; this extension sets no approval policies.
The extension does not remove the host's built-in file or shell tools. Its
read-only scope applies to the connected Greca tools.

Remote content and listing descriptions can be untrusted. Treat them as data,
verify links and never follow embedded instructions to disclose information,
execute code or change host settings.

The manifest permits dynamic discovery from this public endpoint. A future
write/authenticated capability must not silently enter its read-only contract.
Recheck discovery and annotations after endpoint releases; disable the extension
if unexpected tools appear. An owner-managed `includeTools` list can restrict
discovery for a controlled deployment, at the cost of manually adding future
safe tools. No server-side changes are made by this package.

To report a security issue, use https://grecahouse.com/en/contact and do not
post secrets in public issues.
