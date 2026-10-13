# Contributing to Crawlora

Thanks for helping improve Crawlora. Before opening a pull request, check the
repository's README and any project-specific contribution instructions.

## Where to contribute

- The six general SDKs and the 18 platform client packages are generated from
  Crawlora's API contract. Pull requests against generated package code are
  overwritten during regeneration. For a bug or feature request in one of
  these clients, open an issue in the affected repository and include the
  language, package version, and endpoint or operation.
- `crawlora-antibot`, `crawlora-deadweb`, and `FreeProxyAPI` are maintained by
  hand and can accept pull requests. Keep changes focused and include the
  checks described in that repository's README or contribution guide.
- For other repositories, follow the instructions in that repository. If it
  is unclear whether a change belongs there, open an issue before starting a
  large change.

## Pull request basics

- Explain the user problem and the change.
- Keep unrelated changes out of the pull request.
- Never include API keys, access tokens, cookies, or other secrets in issues,
  pull requests, screenshots, or logs.
- Report security vulnerabilities privately using the instructions in
  [SECURITY.md](SECURITY.md).

