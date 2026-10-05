# Data handling

The extension consists of configuration and documentation. It stores no keys
and runs no local executable, hooks or telemetry code.

When Gemini invokes a Greca tool, the MCP client sends the selected tool name
and arguments to `https://grecahouse.com/mcp` over HTTPS. Arguments can include
budget, location, desired property features, listing reference, language, and
purchase-cost inputs. Greca returns public listing/research data or an estimate.

This is not a claim that the entire conversation is sent to Greca, nor a
guarantee about exactly which information the model will place in arguments.
The host processes prompts and results under its own account settings and
privacy terms. Network connections also expose ordinary request metadata to
the endpoint and its service providers.

Do not supply credentials, private CRM information, passports or applicant
documents. They are unnecessary for the supported public read-only tools.

On the server, Greca House's privacy policy (section "Greca House in AI assistants",
https://grecahouse.com/en/privacy-policy) applies: each request is recorded in the
hosting provider's standard request logs (time, path, result, the calling server's
address and software, response time) together with which tool ran and whether it
succeeded, without the details asked for. These logs are kept for 30 days; a one-way
hash of the calling address is kept for up to 24 hours to prevent abuse. The tools
create no enquiry and store no request.
