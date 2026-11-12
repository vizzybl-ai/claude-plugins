# Vizzybl

Vizzybl measures how your brand appears inside AI answers. This plugin lets you ask Claude about it in plain words: how your share of voice moved this week, which AI engines mention you least, what ChatGPT or Perplexity actually said about you, which websites get cited for your topics when you are not, and what to fix first.

It covers eight engines: ChatGPT, Claude, Gemini, Perplexity, Grok, Copilot, Google AI Overviews and Google AI Mode.

## What you need

- A Vizzybl workspace on the **Ultra** or **Enterprise** plan. You approve the connection as an owner or admin of that workspace.
- The **Vizzybl** connector, which comes with this plugin. On claude.ai and in Cowork, open the plugin's **Connectors** tab and choose **Connect**. In Claude Code it connects on first use. Either way you sign in with your Vizzybl account; no API key is needed.

## Use it

Ask in your own words, for example:

- "How did we do in AI answers this week?"
- "Which AI engine mentions us least?"
- "What did ChatGPT say about us for 'best CRM for agencies'?"
- "Which sites get cited for our topics where we don't?"
- "Run a GEO audit on example.com/pricing."

The plugin's skills tell Claude which Vizzybl tool answers which question and how to read the numbers. In Claude Code they are also commands: `/vizzybl:pulse`, `/vizzybl:scorecard`, `/vizzybl:answers`, `/vizzybl:gaps`, `/vizzybl:audit` and `/vizzybl:visibility`.

## What costs credits

Reading your data is free. Three actions change your workspace or spend its credits, and Claude asks you before each one:

- running a GEO audit on a URL (spends credits);
- fetching fresh AI answers for a prompt now (spends credits);
- adding monitored prompts (free, but they count toward your plan's prompt limit).

## Data

The plugin's skills call the Vizzybl connector at `mcp.vizzybl.ai`, which reads your Vizzybl workspace: brand details, monitored prompts, the AI answers Vizzybl collected for them, citations, visibility scores, recommendations, AI-crawler traffic and audits. The three actions above are the only ones that change anything. The plugin itself stores nothing and sends nothing anywhere else. Sign-in uses your Vizzybl account, and you can disconnect at any time in Vizzybl under **Settings → API Keys → Connected AI apps**.

How Vizzybl handles your data: https://vizzybl.ai/privacy

## Help

- Connector and tool reference: https://vizzybl.ai/docs/integrations/mcp
- Vizzybl: https://vizzybl.ai
