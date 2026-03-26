# Power Platform DevOps Studio Releases

This repository hosts the packaged releases for **Power Platform DevOps Studio**.

If you just want to install and run Studio, start from the [Releases](https://github.com/dylanhaskins/PowerPlatform-DevOpsStudio-Releases/releases) page.

## What each release contains

Each tagged release publishes:

- Windows x64 bundled archive: `PowerPlatform-DevOpsStudio-win-x64-v<version>.zip`
- macOS Apple Silicon bundled archive: `PowerPlatform-DevOpsStudio-macos-arm64-v<version>.tar.gz`
- Linux x64 bundled archive: `PowerPlatform-DevOpsStudio-linux-x64-v<version>.tar.gz`
- Windows installer script: `Install-DevOpsStudio.ps1`
- macOS/Linux installer script: `install-devops-studio.sh`
- Plain-text install guide: `INSTALL.txt`
- `CHANGELOG.md`

The bundled archives already include the prebuilt Studio app and launch scripts.

## Recommended install

The easiest path is to use the installer script attached to the latest release.

### Windows

```powershell
Invoke-WebRequest 'https://github.com/dylanhaskins/PowerPlatform-DevOpsStudio-Releases/releases/latest/download/Install-DevOpsStudio.ps1' -OutFile "$env:TEMP\Install-DevOpsStudio.ps1"; & "$env:TEMP\Install-DevOpsStudio.ps1"
```

### macOS / Linux

```bash
curl -fsSL https://github.com/dylanhaskins/PowerPlatform-DevOpsStudio-Releases/releases/latest/download/install-devops-studio.sh | bash
```

These installers:

- download the correct release asset for the platform
- install into a user-writable location
- create a launcher or shortcut where supported
- start Studio automatically after install

## Install a specific version

### Windows

```powershell
Invoke-WebRequest 'https://github.com/dylanhaskins/PowerPlatform-DevOpsStudio-Releases/releases/download/v1.0.96/Install-DevOpsStudio.ps1' -OutFile "$env:TEMP\Install-DevOpsStudio.ps1"; & "$env:TEMP\Install-DevOpsStudio.ps1" -Version 1.0.96
```

### macOS / Linux

```bash
curl -fsSL https://github.com/dylanhaskins/PowerPlatform-DevOpsStudio-Releases/releases/download/v1.0.96/install-devops-studio.sh | bash -s -- --version 1.0.96
```

## Manual install

If you prefer not to use the installer script:

1. Open the [Releases](https://github.com/dylanhaskins/PowerPlatform-DevOpsStudio-Releases/releases) page.
2. Download the archive for your platform.
3. Extract it to a folder you control.
4. Start Studio with:
   - `Start-DevOpsStudio.ps1` on Windows
   - `start-devops-studio.sh` on macOS/Linux

## Runtime requirements

Studio bundled releases still require:

- [Node.js 18+](https://nodejs.org)
- [Power Platform CLI (pac)](https://aka.ms/PowerAppsCLI)
- [Azure CLI (az)](https://learn.microsoft.com/cli/azure/install-azure-cli)
- [Git](https://git-scm.com/)

Some features may also rely on other tooling such as the .NET SDK, depending on the workflow you use inside Studio.

## What Studio helps with

Power Platform DevOps Studio provides a browser-based workspace for:

- Power Platform solution export and unpack
- source control and Azure DevOps setup
- local deployment runner workflows
- environment and authentication checks
- Dataverse type generation
- Studio Agent and MCP-powered operations when licensed and enabled

## Updates

Bundled installs check for newer releases and can surface a download link when an update is available.

If you need the quickest install steps for a specific version, open that version's release page and use the attached `INSTALL.txt` asset.
