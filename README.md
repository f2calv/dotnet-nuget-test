# GitHub Action .NET NuGet Test

This repository is a small .NET 10 package and test project used to validate the account's reusable
NuGet build, test, pack, Trusted Publishing and release workflows.

## Projects

- `src/CasCap.NuGetTestLib` is the packable sample library.
- `src/CasCap.NuGetTestLib.Tests` verifies the library through xUnit and
  Microsoft.Testing.Platform.

## Development

Open `dotnet-nuget-test.slnx` with the .NET 10 SDK selected. The Dev Container provides the matching
.NET toolchain and pre-commit; it reports the SDK version at startup but does not mutate dependencies
or install Git hooks.

Run repository linting explicitly:

```text
pre-commit run --all-files
```

Restore, build and test commands require NuGet access and are intentionally left to the developer.

## Continuous Integration

Pull requests run reusable lint and version calculation jobs, then build and test the solution
through `f2calv/gha-dotnet-nuget`. Trusted default-branch runs may publish packages and create
immutable GitHub releases. A manually authorized preview run may publish a prerelease package, but
does not create a GitHub release. NuGet API keys are intentionally unsupported so an OIDC failure
cannot be hidden by a fallback credential.

## License

This project is licensed under the [MIT License](LICENSE).
