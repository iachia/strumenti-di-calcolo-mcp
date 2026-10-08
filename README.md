# Strumenti di calcolo dello Studio Notarile Chianese

Six calculators for Italy from a notary's office: property purchase taxes, cadastral value, usufruct and bare ownership, heirs' shares, inheritance and gift tax, selling versus gifting a home.

This is a remote MCP server, maintained by Studio Notarile Chianese, a notary's office in Pioltello and Milan, Italy. The calculators are built on the same calculators anyone can use on the office's website, at [notaiochianese.it/strumenti](https://www.notaiochianese.it/strumenti/), with the same figures, which the office updates when they change.

This repository holds only this description. The server is hosted by the office, and its source code is not published here.

## What it calculates

| Tool | What it calculates |
| --- | --- |
| `imposte_acquisto_casa` | The taxes on buying real estate: a home or an outbuilding, land, an office, a shop or a warehouse, from a private seller or from a company, with and without first-home relief, including the taxes on a mortgage loan |
| `valore_catastale` | The cadastral value of a property from its cadastral income (rendita catastale) and, for an inheritance or a gift, of every asset on a cadastral record, buildings and land |
| `usufrutto_nuda_proprieta` | The value of usufruct and bare ownership, by the age of the person who keeps the usufruct |
| `quote_ereditarie` | Who inherits and in what shares when there is no will, and the share the law reserves to spouse, children and parents |
| `imposte_successione_donazione` | Inheritance tax and gift tax, with the allowances that depend on kinship, from the assets as listed on the cadastral record if needed, and a comparison between the two |
| `vendita_o_donazione` | The taxes on selling and on gifting the same home to a family member, side by side |

Tool names, inputs and results are in Italian, because the calculators apply Italian rules. Every tool description ends with a summary in English.

## How to configure it

The server address is:

```
https://mcp.notaiochianese.it/mcp
```

Streamable HTTP, no authentication, read-only. No account and no password are needed.

In VS Code, run **MCP: Add Server** from the Command Palette and paste the address, or add the server to `.vscode/mcp.json`:

```json
{
  "servers": {
    "notaio-chianese-calcoli": {
      "type": "http",
      "url": "https://mcp.notaiochianese.it/mcp"
    }
  }
}
```

In any other assistant that speaks the Model Context Protocol, look in the settings for connectors, or MCP servers, add a new one and paste the address.

## How to use it

Ask in your own words: the assistant calls the calculator and reports the result. For example:

- How much tax will I pay buying a €200,000 first home in Italy from a private seller? Cadastral income is €900.
- My father died in Italy without a will, leaving his wife and three children. Who inherits, and in what shares?
- In Italy, is it cheaper in taxes to sell or to gift my flat to my son? Cadastral income €1,000, value €150,000.

## What every answer contains

The items one by one, the date the figures were last checked, what the calculation leaves out, and the address of the calculator's page on the office's website.

These are calculations: not a fee quote, because they do not include the notary's fee, and not advice on a specific case.

## What the server records

The server is read-only and needs no login. It sends nothing to the notary's office and does not record what is asked: it only counts how many times each calculator is used.

## Links

- Documentation: <https://www.notaiochianese.it/en/calculators-for-ai-assistants/>
- Terms of use: <https://www.notaiochianese.it/en/calculators-for-ai-assistants/terms/>
- Privacy policy: <https://www.notaiochianese.it/en/privacy-policy/>
- Name in the official MCP Registry: `it.notaiochianese/strumenti-di-calcolo`

To report a calculation that looks wrong, or a connection that does not work, write to <notaio@notaiochianese.it>.
