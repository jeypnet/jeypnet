## I build AI agents, MCP servers, and LLM-powered automation.

Most of what I ship is agent shaped. A model, a set of tools I wrote for it, and a real system on the other end that is not allowed to break.

The interesting work is never the prompt. It is the tool schema an LLM can actually use without guessing, the sanitizing on anything that flows back into a model's context, the fallback path for when the API is down, and the logging that lets you prove what the agent did after it did it.

I am a Customer Success Manager at [JoGo.Team](https://jogo.team), and I build the platform's AI layer.

---

## Live proof: the JoGo.Team MCP server

I wrote and run the Model Context Protocol server that lets any AI assistant find and book pickup soccer through JoGo.Team. It is public. You can call it right now, from your own terminal, without a key:

```bash
curl -s -X POST https://jogo.team/mcp \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

What comes back:

- **MCP protocol `2025-06-18`**, advertising tools, prompts, and resources
- **5 tools**: `search_cities`, `list_games`, `get_venue`, `get_platform_overview`, `host_a_game`
- **3 prompts** plus a `jogo://about` resource for positioning context
- Tool descriptions written for the model, not for a human. They tell the assistant when to reach for the tool instead of falling back to web search, and they state plainly that a game not returned by the call must never be advertised as available.

Beyond the read-only surface it also carries authenticated write tools for hosts, off by default and scoped per host, so an assistant can draft and publish a real game. Every tool call is logged so adoption is measurable rather than assumed.

Building it taught me the things you only learn by shipping an agent surface to strangers: models will call your tool with the wrong shape, they will happily invent a city you do not serve, and anything you hand back becomes context you no longer control.

---

## What is here

| Repo | What it is |
|---|---|
| [csm-account-intelligence](https://github.com/jeypnet/csm-account-intelligence) | Churn-risk scoring plus QBR briefs generated through the OpenAI API, with a deterministic fallback so it still runs with no key. Ships a customer-facing PDF report. Synthetic sample data. |
| [twilio-whatsapp-reengagement](https://github.com/jeypnet/twilio-whatsapp-reengagement) | Retention automation that scores engagement health, flags at-risk users, and fires personalized Twilio SMS and WhatsApp messages. Reactivated 80%+ of dormant users in production. |
| [flexradio-smartsdr-client](https://github.com/jeypnet/flexradio-smartsdr-client) | Python client for the FlexRadio SmartSDR TCP/IP API. UDP discovery, slice tuning, live SWR and power meters, streaming callbacks. |
| [hf-propagation-checker](https://github.com/jeypnet/hf-propagation-checker) | Live radio propagation scoring off the NOAA space weather APIs. No keys, no paid services. |

---

## What I work with

**AI and agents**
Model Context Protocol (MCP) servers and clients, tool and schema design, Claude Code, Anthropic and OpenAI APIs, prompt engineering, multi-agent orchestration, browser-driving agents, scheduled autonomous loops, human in the loop review

**Building and shipping**
Python, Django on Render, REST and JSON-RPC API integration, Stripe Connect, Twilio SMS and WhatsApp Business API, SendGrid, Cloudflare WAF and DNS and CDN, GitHub Actions, Sentry, Supabase, pytest

**Measuring**
GA4 Data API, Google Search Console, customer health scoring, churn signal detection

---

## Before this

I came to AI engineering from customer-facing technical roles, which is why I build agents that have to survive contact with real users rather than demos.

- **BP3 Global**, Senior Enterprise Sales Executive. I worked Fortune 500 accounts in banking and manufacturing across AI and automation.
- **Konica Minolta**, Sales Executive. Public sector accounts, cloud document and AI security platforms.
- **FlexRadio Systems**, Sales Manager. Software-defined radio into defense, utilities, and emergency response.
- **Motorola BGH**, Lab Technician. First iDEN certified technician in Latin America.

Bachelor of Engineering, UTN FRBA, Argentina. FCC Extra Class amateur radio license. Bilingual English and Spanish.

---

Open to remote AI Developer, AI Solutions Developer, and AI Solutions Engineer roles.
[LinkedIn](https://www.linkedin.com/in/jeypnet/)
