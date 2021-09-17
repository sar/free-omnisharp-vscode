# [LTS] FOSS C# Debugger & OmniSharp for VS Code-like Editors

C# Debugging is only supported in official Microsoft-signed binary blob releases of VS Code due to [License](https://aka.ms/VSCode-DotNet-DbgLicense) restrictions and is considered proprietary.

This extension replaces `NetCoreDbg` with [Samsung's MIT-licensed alternative](https://github.com/Samsung/netcoredbg/blob/master/LICENSE).

## About LTS Fork

Long-Term Support fork tracks upstream changes built and tested across different platforms. Each release is pegged to provide maximum stability, security, and usability to prevent developer downtime.

**Dependency Versions**

↗ [NetCoreDbg-LTS](https://github.com/sar/netcoredbg-LTS): Release `1.20.786` \
↗ [OmniSharp-VSCode](https://github.com/OmniSharp/omnisharp-vscode): Release `1.23.15`

**Tested Deployments**

✔ [Code-Server](https://github.com/sar/vs-code-server-with-ssl) Containers
  * Release `3.12.0`
  * VS Code Release `1.6.0`

✔ [VS Codium](https://github.com/VSCodium/vscodium)
  * Release `1.60.1`

✔ [Microsoft/VSCode - Code-OSS](https://github.com/microsoft/vscode)
  * Release `1.60.1`

⚠ [GitPod](https://github.com/gitpod-io/gitpod)
  * Debugger fails due to dependency on dotnet runtime env issue [#5090](https://github.com/gitpod-io/gitpod/issues/5090)

---

## Installation

This extension is published at [open-vsx.org](https://open-vsx.org/extension/sar/csharp) using Github Actions CI/CD Pipeline.

### Build from source

Requirements:

- [nodejs](https://nodejs.org)
- npm (comes with nodejs)

```bash
git clone https://github.com/muhammadsammy/free-omnisharp-vscode.git

cd free-omnisharp-vscode

npm install

npx gulp 'vsix:release:package'

```

then run `Extensions: Install from VSIX` from the command pallete and select the `csharp-VERSION_NUMBER.vsix` file.

# From [OmniSharp/omnisharp-vscode](https://github.com/OmniSharp/omnisharp-vscode) README

## Note about using .NET Core 3.1.40x SDKs

The .NET 3.1.40x SDKs require version 16.7 of MSBuild.

For MacOS and Linux users who have Mono installed, this means you will need to set `omnisharp.useGlobalMono` to `never` until a version of Mono ships with MSBuild 16.7.

## Note about using .NET 5 SDKs

The .NET 5 SDK requires version 16.8 of MSBuild.

For Windows users who have Visual Studio installed, this means you will need to be on the latest Visual Studio 16.8 Preview.
For MacOS and Linux users who have Mono installed, this means you will need to set `omnisharp.useGlobalMono` to `never` until a version of Mono ships with MSBuild 16.8.

### Emmet support in Razor files

To enable emmet support, add the following to your settings.json:

```json
"emmet.includeLanguages": {
    "aspnetcorerazor": "html"
}
```

### Semantic Highlighting

The C# semantic highlighting support is in preview. To enable, set `editor.semanticHighlighting.enabled` and `csharp.semanticHighlighting.enabled` to `true` in your settings. Semantic highlighting is only provided for code files that are part of the active project.

To really see the difference, try the new Visual Studio 2019 Light and Dark themes with semantic colors that closely match Visual Studio 2019.

### Development

First install:

- Node.js (8.11.1 or later)
- Npm (5.6.0 or later)

To **run and develop** do the following:

- Run `npm i`
- Run `npm run compile`
- Open in Visual Studio Code (`code .`)
- _Optional:_ run `npm run watch`, make code changes
- Press <kbd>F5</kbd> to debug

To **test** do the following: `npm run test` or <kbd>F5</kbd> in VS Code with the "Launch Tests" debug configuration.
