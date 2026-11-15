# SpendCanary free Google Ads tools (MCP server)

A free, remote [MCP](https://modelcontextprotocol.io) server with SpendCanary's Google Ads and PPC calculators and checkers, for Claude, ChatGPT and other AI assistants. Works with Google Ads.

```
https://spendcanary.com/mcp
```

- **No sign-in, no API key.** Streamable HTTP, stateless.
- **Never reads a Google Ads account.** The tools only work on the numbers and text you give them.
- **Nothing is stored.** Only the tool name, time taken and outcome are logged.

Set-up steps, the tool list and an example result: [spendcanary.com/mcp](https://spendcanary.com/mcp). The same tools on the web: [spendcanary.com/tools](https://spendcanary.com/tools).

## Tools

| Tool                             | What it does                                                                                                   |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `check_ad_copy`                  | Checks Google responsive search ad or Meta ad text against character limits and common rejection reasons.      |
| `daily_budget_max_spend`         | The most Google Ads can charge in a day (2× the average daily budget) and in a month (30.4×).                  |
| `roas`                           | Return on ad spend, plus the break-even ROAS and profit for a profit margin.                                   |
| `cpc`                            | Cost per click from spend and clicks (or any two of spend, clicks and CPC), plus CPM and click-through rate.   |
| `search_partners_cost`           | Compares cost per conversion on Google Search and search partners, and what partners cost a month beyond it.   |
| `wasted_spend_from_search_terms` | Totals the spend on search terms with no conversions from a search terms report (CSV text).                    |
| `check_landing_page`             | Loads a public landing page on a phone and a computer: speed, redirects, a way to call or buy, the Google tag. |

Every result starts with a one-line summary, then the details, then one link to the matching tool or guide on spendcanary.com.

## Add it

**Claude:** Customize › Connectors › + Add › Add custom connector. Paste the address, click Continue, choose **No sign in**, then Add. ([Claude help](https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp))

**Claude Code:**

```sh
claude mcp add --transport http spendcanary https://spendcanary.com/mcp
```

**ChatGPT:** turn on developer mode in ChatGPT's settings, create a connector with the address above, and choose no authentication. Plans and menu names change; see OpenAI's help centre.

**Other clients:** any client that supports remote Streamable HTTP servers, with the address above and no authentication.

## Limits

A few calls a minute per IP address, and 5 landing page checks an hour. The landing page check only fetches public web pages.

## Want it to check your own account?

The free, read-only [SpendCanary scan](https://spendcanary.com/scan/script?utm_source=github&utm_medium=readme&utm_campaign=mcp-free-tools) finds the wasted spend in your Google Ads account, with a monthly dollar figure on each problem.

---

This repository holds the server's listing files (`server.json`, this README). The server runs at the address above.
