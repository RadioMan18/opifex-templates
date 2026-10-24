# Opifex Agent Templates

Community agent templates for Opifex v1.1.0+. This repository hosts the template catalog used by Opifex's built-in Agent Template Marketplace.

## Catalog Format

`catalog.json` at the repo root lists available agent templates. Each entry:

```json
{
  "id": "research-summarizer",
  "name": "Research Summarizer",
  "description": "Summarizes web research into a briefing doc with citations.",
  "version": "1.0.0",
  "author": "community",
  "downloadUrl": "https://github.com/RadioMan18/opifex-templates/releases/download/research-summarizer-1.0.0/research-summarizer-1.0.0.zip",
  "checksum": "sha256:abc123...",
  "specJson": { ... },
  "model": "ollama",
  "isStarter": false
}
```

Templates can be distributed either inline (`specJson`) or as a signed zip (`downloadUrl` + `checksum`).

## Adding a Template

1. Create a release with your template zip attached.
2. Compute the SHA-256 checksum of the zip.
3. Add an entry to `catalog.json` with `downloadUrl` and `checksum`.
4. Open a pull request.

## Checksum

```powershell
Get-FileHash -Algorithm SHA256 path/to/template.zip
```

Prefix the hex digest with `sha256:` in the catalog entry.

## Using with Opifex

In Opifex v1.1.0+, go to **Agent Library → 📦 Template Marketplace** and add this catalog URL:

```
https://raw.githubusercontent.com/RadioMan18/opifex-templates/main/catalog.json
```

Then browse, install, and use community agent templates.

## License

MIT
