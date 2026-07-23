# Deployment Theory 🚀

### Open-source Go building blocks for modern endpoint & device management.

From **config-as-code** down to **raw OS bindings** — cross-platform tooling for the modern workplace, all in Go.

`macOS` · `Windows` · `Apple` · `Jamf Pro` · `Jamf Protect` · `Intune / Microsoft 365` · `Entra ID`

> **For** Mac admins, Windows endpoint engineers, and modern-workplace / EUC platform teams who want to manage devices the way software teams ship code — versioned, tested, automated.

We started as Terraform providers for Jamf Pro & Microsoft 365. Today we're a full-stack Go ecosystem for endpoint management — **from the Terraform plan all the way down to the Win32 syscall.**

---

## What we build

- [① Config as Code — Terraform](#-config-as-code--terraform)
- [② Go API SDKs](#-go-api-sdks)
- [③ Low-level platform bindings](#-low-level-platform-bindings)
- [④ Systems & OS-level tooling](#-systems--os-level-tooling)
- [⑤ Security & threat intelligence](#-security--threat-intelligence)
- [⑥ CLIs, automation & AI/MCP](#-clis-automation--aimcp)

---

## ① Config as Code — Terraform

Where we started: manage your device estate as version-controlled, peer-reviewed, pipeline-deployed code.

| Repository | What it does | Lang | ★ |
|---|---|:--:|:--:|
| **[terraform-provider-jamfpro](https://github.com/deploymenttheory/terraform-provider-jamfpro)** | Terraform provider for Jamf Pro — config-as-code for Apple device management across the classic & Jamf Pro APIs | Go | ![](https://img.shields.io/github/stars/deploymenttheory/terraform-provider-jamfpro?style=flat&label=&color=444) |
| **[terraform-provider-microsoft365](https://github.com/deploymenttheory/terraform-provider-microsoft365)** | Terraform provider for Microsoft 365 — Intune, Entra ID & Graph (v1.0 + beta) as code | Go | ![](https://img.shields.io/github/stars/deploymenttheory/terraform-provider-microsoft365?style=flat&label=&color=444) |
| **[terraform-training-jamfpro](https://github.com/deploymenttheory/terraform-training-jamfpro)** | Hands-on Terraform + GitOps training for workplace engineers | HCL | ![](https://img.shields.io/github/stars/deploymenttheory/terraform-training-jamfpro?style=flat&label=&color=444) |
| **[terraform-demo-jamfpro-v2](https://github.com/deploymenttheory/terraform-demo-jamfpro-v2)** | Reference GitHub Actions + Terraform Cloud pipeline for Jamf Pro | HCL | ![](https://img.shields.io/github/stars/deploymenttheory/terraform-demo-jamfpro-v2?style=flat&label=&color=444) |
| **[terraform-demo-microsoft365](https://github.com/deploymenttheory/terraform-demo-microsoft365)** | Reference GitLab-branching + Terraform pipeline for Microsoft 365 | HCL | ![](https://img.shields.io/github/stars/deploymenttheory/terraform-demo-microsoft365?style=flat&label=&color=444) |
| **[jamftf-python-terraform-importer](https://github.com/deploymenttheory/jamftf-python-terraform-importer)** | Import an existing Jamf Pro estate into Terraform state | Python | ![](https://img.shields.io/github/stars/deploymenttheory/jamftf-python-terraform-importer?style=flat&label=&color=444) |

## ② Go API SDKs

Typed, idiomatic Go clients for the tools that run the modern workplace — the layer the providers and CLIs are built on.

| Repository | What it does | Lang | ★ |
|---|---|:--:|:--:|
| **[go-api-sdk-jamfpro](https://github.com/deploymenttheory/go-api-sdk-jamfpro)** | Mature Go SDK for the Jamf Pro classic + modern APIs with full CRUD, plus examples & recipes | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-api-sdk-jamfpro?style=flat&label=&color=444) |
| **[go-sdk-jamfpro-v2](https://github.com/deploymenttheory/go-sdk-jamfpro-v2)** | Next-gen Jamf Pro SDK — full API surface coverage (700+ functions) | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-sdk-jamfpro-v2?style=flat&label=&color=444) |
| **[go-sdk-jamfprotect](https://github.com/deploymenttheory/go-sdk-jamfprotect)** | Go SDK for Jamf Protect with full API surface coverage | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-sdk-jamfprotect?style=flat&label=&color=444) |
| **[go-sdk-appleservices](https://github.com/deploymenttheory/go-sdk-appleservices)** | Go SDK for Apple enterprise services — ABM, DDM, MDM, notarization & iTunes | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-sdk-appleservices?style=flat&label=&color=444) |
| **[go-sdk-sofa](https://github.com/deploymenttheory/go-sdk-sofa)** | Go SDK for SOFA — the MacAdmins feed for Apple software updates | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-sdk-sofa?style=flat&label=&color=444) |
| **[go-sdk-workbrew](https://github.com/deploymenttheory/go-sdk-workbrew)** | Go SDK for Workbrew — Homebrew fleet management | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-sdk-workbrew?style=flat&label=&color=444) |
| **[go-sdk-nexthink](https://github.com/deploymenttheory/go-sdk-nexthink)** | Go SDK for Nexthink digital-experience data | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-sdk-nexthink?style=flat&label=&color=444) |
| **[go-lib-winget-pkgs](https://github.com/deploymenttheory/go-lib-winget-pkgs)** | Query WinGet package metadata from a local clone — no external API calls | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-lib-winget-pkgs?style=flat&label=&color=444) |
| **[go-api-http-client](https://github.com/deploymenttheory/go-api-http-client)** | The modular HTTP client that powers the SDKs — auth, retries & pagination | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-api-http-client?style=flat&label=&color=444) |

<sub>Also: [go-sdk-brew](https://github.com/deploymenttheory/go-sdk-brew) · [go-sdk-chocolatey](https://github.com/deploymenttheory/go-sdk-chocolatey) — package-manager SDKs.</sub>

## ③ Low-level platform bindings

Idiomatic Go, generated from vendor metadata — the whole OS API surface, typed and callable. This is the depth that sets Deployment Theory apart.

| Repository | What it does | Lang | ★ |
|---|---|:--:|:--:|
| **[go-bindings-win32](https://github.com/deploymenttheory/go-bindings-win32)** | Idiomatic Go bindings for the Win32 API — every function, struct, enum & COM interface, generated from Microsoft's win32metadata | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-bindings-win32?style=flat&label=&color=444) |
| **[go-bindings-macosplatform](https://github.com/deploymenttheory/go-bindings-macosplatform)** | Go ↔ Objective-C / C bridge and bindings for macOS platform frameworks (purego + cgo), with Clang AST metadata | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-bindings-macosplatform?style=flat&label=&color=444) |
| **[go-bindings-winrt](https://github.com/deploymenttheory/go-bindings-winrt)** | Go bindings for the Windows Runtime — toasts, Bluetooth LE, Windows Hello, MDM/provisioning | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-bindings-winrt?style=flat&label=&color=444) |
| **[go-bindings-wdk](https://github.com/deploymenttheory/go-bindings-wdk)** | Go bindings for the Windows Driver Kit surface (Windows.Wdk.*), from Microsoft's wdkmetadata | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-bindings-wdk?style=flat&label=&color=444) |
| **[go-bindings-wmi](https://github.com/deploymenttheory/go-bindings-wmi)** | Typed Go bindings for WMI / CIM classes from a committed schema snapshot | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-bindings-wmi?style=flat&label=&color=444) |
| **[go-winmd](https://github.com/deploymenttheory/go-winmd)** | The shared metadata parser underpinning the whole Windows bindings family | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-winmd?style=flat&label=&color=444) |

## ④ Systems & OS-level tooling

Pure-Go implementations of things that usually need C, DISM, or a hypervisor — built for CI/CD and cross-platform automation.

| Repository | What it does | Lang | ★ |
|---|---|:--:|:--:|
| **[go-sdk-vtpm2](https://github.com/deploymenttheory/go-sdk-vtpm2)** | Pure-Go software TPM 2.0 (vTPM) — measured boot, BitLocker sealing & attestation for Windows 11 guests under QEMU | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-sdk-vtpm2?style=flat&label=&color=444) |
| **[go-apfs](https://github.com/deploymenttheory/go-apfs)** | Go toolkit for handling Apple File System (APFS) volumes on Linux & Windows, targeting CI/CD | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-apfs?style=flat&label=&color=444) |
| **[go-sdk-winmediafoundry](https://github.com/deploymenttheory/go-sdk-winmediafoundry)** | Pure-Go toolkit + CLI for acquiring & building Windows install media — no wimlib, DISM, oscdimg or cabextract | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-sdk-winmediafoundry?style=flat&label=&color=444) |
| **[go-sdk-windowscsp](https://github.com/deploymenttheory/go-sdk-windowscsp)** | Go SDK for Windows Configuration Service Providers — typed LCRUD from DDF v2, with OMA-DM SyncML | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-sdk-windowscsp?style=flat&label=&color=444) |
| **[go-appdeploymenttoolkit](https://github.com/deploymenttheory/go-appdeploymenttoolkit)** | A Go port of the PowerShell App Deployment Toolkit (PSADT) | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-appdeploymenttoolkit?style=flat&label=&color=444) |

## ⑤ Security & threat intelligence

Feeds and primitives for building security into device management — vulnerability data, file reputation, and hardware attestation.

| Repository | What it does | Lang | ★ |
|---|---|:--:|:--:|
| **[go-sdk-virustotal](https://github.com/deploymenttheory/go-sdk-virustotal)** | Go client for VirusTotal API v3 — file/URL scanning & threat intel | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-sdk-virustotal?style=flat&label=&color=444) |
| **[go-sdk-cve](https://github.com/deploymenttheory/go-sdk-cve)** | Go SDK for the NVD CVE API — single CVEs or bulk retrieval | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-sdk-cve?style=flat&label=&color=444) |
| **[go-api-sdk-mitrecve](https://github.com/deploymenttheory/go-api-sdk-mitrecve)** | Go SDK for MITRE CVE services | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-api-sdk-mitrecve?style=flat&label=&color=444) |

<sub>See also [go-sdk-vtpm2](https://github.com/deploymenttheory/go-sdk-vtpm2) for measured boot & TPM attestation.</sub>

## ⑥ CLIs, automation & AI/MCP

The operational glue — command-line tools, packaging pipelines, and an MCP server that brings AI agents to your device estate.

| Repository | What it does | Lang | ★ |
|---|---|:--:|:--:|
| **[jamfpro-mcp-server](https://github.com/deploymenttheory/jamfpro-mcp-server)** | Model Context Protocol server for Jamf Pro — connect AI agents to your device estate | Go | ![](https://img.shields.io/github/stars/deploymenttheory/jamfpro-mcp-server?style=flat&label=&color=444) |
| **[macos-autopkg-factory](https://github.com/deploymenttheory/macos-autopkg-factory)** | GitHub Actions macOS package factory built on AutoPkg, Suspicious Package & Go | Go | ![](https://img.shields.io/github/stars/deploymenttheory/macos-autopkg-factory?style=flat&label=&color=444) |
| **[go-jamf-guid-sharder](https://github.com/deploymenttheory/go-jamf-guid-sharder)** | CLI that shards Jamf Pro GUID lists into deployment groups by rule | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-jamf-guid-sharder?style=flat&label=&color=444) |
| **[go-jamf-service-status](https://github.com/deploymenttheory/go-jamf-service-status)** | Tools that parse and analyse Jamf's service-status RSS feed | Go | ![](https://img.shields.io/github/stars/deploymenttheory/go-jamf-service-status?style=flat&label=&color=444) |
| **[workplace-devtools-jamfpro](https://github.com/deploymenttheory/workplace-devtools-jamfpro)** | A collection of tools, apps & scripts for managing macOS with Jamf Pro | Shell | ![](https://img.shields.io/github/stars/deploymenttheory/workplace-devtools-jamfpro?style=flat&label=&color=444) |

---

## 🤝 Community & contributing

Built for the community, by the community. Mac admins, Windows endpoint engineers, and DevOps practitioners all welcome.

- **Slack** — find us on the [Mac Admins Slack](https://macadmins.slack.com/archives/C06R172PUV6) (`#terraform-provider-jamfpro`)
- **Discussions** — GitHub Discussions on each repository
- **Issues & PRs** — bug reports, feature requests and contributions welcome across every repo

## 💡 Principles

- **Everything as Code** — if it can be configured, it should be versioned, tested and automated
- **Idiomatic Go** — typed, generated from source-of-truth metadata, and pleasant to call
- **Cross-platform** — macOS and Windows are first-class, not afterthoughts
- **Community first** — open source, transparent, and built in the open

---

*Made with ❤️ by the Deployment Theory team*
