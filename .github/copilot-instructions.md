# Copilot Instructions

## Shared Instructions

Shared Copilot instructions, skills and prompts are maintained centrally in the
[account-level .github repository](https://github.com/f2calv/.github). They are deliberately not
copied here. Clone that repository and add it to the VS Code workspace, or link its instruction
folders into `~/.copilot/`. If the shared files are unavailable, stop rather than guessing the
conventions.

Everything below is specific to this repository.

## Repository Purpose

This repository is the public canary for building, testing, packing and publishing a small .NET
NuGet package through the reusable account workflows.

- Build and test `dotnet-nuget-test.slnx`; keep package versions centralized.
- Preserve `CasCap.NuGetTestLib` as the intentionally packable project and keep its test project
  under `src/`.
- Keep NuGet Trusted Publishing credentialless. Do not add a fallback API key that could conceal an
  OIDC failure.
- Keep pull-request validation safe: packages and releases may be published only by the existing
  trusted workflow conditions.
- Do not broaden the sample API merely to exercise packaging.
