<div align="center">

# The Code Codex

**Study notes, hands-on guides and open-source tools for developers — in Portuguese and English.**

[thecodecodex.com](https://thecodecodex.com) · [Tools](https://thecodecodex.com/pt/tools/) · [`cli.js`](https://thecodecodex.com/cli.js) · [npm](https://www.npmjs.com/org/thecodecodex)

</div>

---

## What we build

| Project | What it is | Stack | |
| --- | --- | --- | --- |
| [**portal**](https://github.com/thecodecodex/portal) | The [thecodecodex.com](https://thecodecodex.com) website: guides, notes, projects and ~20 client-side tools (CLT/PJ salary, invoices, PDF Studio, CPF/CNPJ, JWT, regex, diff…) | Astro · Preact · Tailwind 4 · Pagefind · Cloudflare | 🔒 private |
| [**tools**](https://github.com/thecodecodex/tools) | Pure logic behind every tool, the zero-dependency terminal script `cli.js` and a catalog of AI agent skills | TypeScript · Vitest | [![npm](https://img.shields.io/npm/v/@thecodecodex/tools?label=%40thecodecodex%2Ftools)](https://www.npmjs.com/package/@thecodecodex/tools) |
| [**design-system**](https://github.com/thecodecodex/design-system) | Tokens, five themes (light, paper, dusk, dark, high contrast) and form components shared by every project | Tailwind 4 · React (Preact-compatible) | [![npm](https://img.shields.io/npm/v/@thecodecodex/design-system?label=%40thecodecodex%2Fdesign-system)](https://www.npmjs.com/package/@thecodecodex/design-system) |
| [**switchyard**](https://github.com/thecodecodex/switchyard) | Local hub for teams working across many repositories: git dashboard, Azure Boards, GitHub PRs, E2E tests, mocks, databases and cloud logs — a web panel plus the `syd` CLI | Next.js · Go | 🔒 private |

```mermaid
flowchart LR
  ds["@thecodecodex/design-system<br/>tokens · themes · components"]
  tools["@thecodecodex/tools<br/>logic · cli.js · AI skills"]
  portal["portal<br/>thecodecodex.com"]
  sy["switchyard<br/>panel + syd CLI"]
  ds --> portal
  ds -.-> sy
  tools --> portal
  portal -- "ships" --> cli["thecodecodex.com/cli.js"]
```

## Principles

- **Everything runs on your machine.** The tools process data in the browser; nothing is uploaded.
- **One logic, many surfaces.** The same functions power the website, the terminal (`cli.js`) and the tests.
- **Open where it matters.** The logic (`tools`) and the visual language (`design-system`) are MIT-licensed and published to npm with provenance.
- **Accessible by default.** Theme colours are chosen for text contrast (including a high-contrast theme), chart colours are validated for colour-vision deficiencies, and keyboard focus is always visible.
- **Bilingual.** Content and tools exist in Portuguese and English, with the same URL parameters in both.

## Try it from the terminal

Every tool on the site also runs outside the browser, with the same parameters as its URL:

```sh
deno run -q "https://thecodecodex.com/cli.js?tool=net-salary&bruto=8000"   # net salary as JSON
curl -s https://thecodecodex.com/cli.js | node --input-type=module - cpf q=3 # three valid test CPFs
deno run -q "https://thecodecodex.com/cli.js"                                # list every tool
```

## Use our packages

```sh
pnpm add @thecodecodex/tools          # finance (BR), CPF/CNPJ, PDF, table conversion, regex, JWT…
pnpm add @thecodecodex/design-system  # Tailwind 4 tokens, themes and React components
```

```ts
import { isValidCpf } from "@thecodecodex/tools/br/cpf"
import { NumberField, Segmented } from "@thecodecodex/design-system"
```
