# Insearcher plugin marketplace

Canonical plugin catalog for public agent tooling maintained by
[`insearcher`](https://github.com/insearcher). Add this marketplace once, then
install individual plugins under the `@insearcher` namespace.

| Plugin | Purpose | Source |
|---|---|---|
| `abq@insearcher` | Local transport between Claude Code and Codex agents | [`insearcher/abq`](https://github.com/insearcher/abq) |
| `vaultctl@insearcher` | Agent workflows for Git-backed Markdown vaults | [`insearcher/vaultctl`](https://github.com/insearcher/vaultctl) |

## Install with Codex

```bash
codex plugin marketplace add insearcher/plugin-marketplace
codex plugin add abq@insearcher
codex plugin add vaultctl@insearcher
```

## Install with Claude Code

```bash
claude plugin marketplace add insearcher/plugin-marketplace
claude plugin install abq@insearcher
claude plugin install vaultctl@insearcher
```

## Migrate the former Vaultctl-hosted catalog

If `insearcher` already points to `insearcher/vaultctl`, remove only the
marketplace registration, then add this repository. Installed plugins and their
product repositories remain separate.

```bash
codex plugin marketplace remove insearcher
codex plugin marketplace add insearcher/plugin-marketplace

claude plugin marketplace remove insearcher
claude plugin marketplace add insearcher/plugin-marketplace
```

## Ownership model

This repository owns catalog manifests, ordering, install policy, and release
pins only. Plugin packages and product code remain in their product
repositories. Catalog entries use pinned Git subdirectories; a product release
updates its own package first and this catalog pin second.
