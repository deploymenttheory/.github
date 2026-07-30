# Deployment Theory

### Endpoint management, rebuilt as Go engineering.

Open-source building blocks for the modern workplace — **from the Terraform plan all the way down to the Win32 syscall.**

`macOS` · `Windows` · `Apple Business Manager` · `Jamf Pro` · `Jamf Protect` · `Intune / Microsoft 365` · `Entra ID`

> **Who it's for** — Workplace and EUC platform teams who want to manage devices the way software teams ship code: versioned, tested, reviewed and automated.

We started with Terraform providers for Jamf Pro and Microsoft 365. Today we're a full-stack Go ecosystem for endpoint management, covering every layer between your pipeline and the operating system.

---

## Why Go

Device management has historically been written in whatever language the vendor shipped an SDK in (if one even exists). PowerShell here, Bash there, Swift or .Net when you need to touch the OS. This fragments tooling, testing and hiring. We picked one language and have gone all in.

- **One static binary, covers every platform.** Cross-compile from CI, ship a single artifact to macOS, Windows and Linux. No runtime, no interpreter, no dependency chain on the endpoint.

---

**Status labels** used throughout:
![](https://img.shields.io/badge/status-GA-3FB950) production-ready, stable API &nbsp;·&nbsp;
![](https://img.shields.io/badge/status-preview-58A6FF) usable now, API may still move &nbsp;·&nbsp;
![](https://img.shields.io/badge/status-experimental-EAAA32) early, spec-complete or lightly exercised

---

## Work we're proud of

**Pure-Go APFS, read *and* write, without a Mac.**
[go-apfs-v2](https://github.com/deploymenttheory/go-apfs-v2) mounts DMGs and raw images, unlocks FileVault volumes, and writes populated volumes, snapshots, volume groups and transparent compression. Validated against Apple's own `fsck_apfs` and `hdiutil`, plus Linux `apfsck`. Linux CI runners can now do work that previously demanded Apple hardware.

**Pure-Go TPM 2.0.**
[go-sdk-vtpm2](https://github.com/deploymenttheory/go-sdk-vtpm2) is a pure go software vTPM built from the TCG specification — measured boot, BitLocker sealing and attestation for Windows 11 guests. No `swtpm`, no C dependency.

**Windows install media with zero external tooling.**
[go-sdk-winmediafoundry](https://github.com/deploymenttheory/go-sdk-winmediafoundry) acquires and builds Windows installation media with no wimlib, no DISM, no oscdimg and no cabextract. One binary, cross-platform.

**The entire Win32 surface, typed and idiomatic.**
[go-bindings-win32](https://github.com/deploymenttheory/go-bindings-win32) generates Go for every function, struct, enum, constant and COM interface in Microsoft's win32metadata — hundreds of namespaces. [WinRT](https://github.com/deploymenttheory/go-bindings-winrt), the [WDK](https://github.com/deploymenttheory/go-bindings-wdk), [WMI](https://github.com/deploymenttheory/go-bindings-wmi) and the [Windows App SDK](https://github.com/deploymenttheory/go-bindings-windowsappsdk) follow the same pattern, all built on the shared [go-winmd](https://github.com/deploymenttheory/go-winmd) parser.

**Windows CSPs as a typed API.**
[go-sdk-windowscsp](https://github.com/deploymenttheory/go-sdk-windowscsp) turns Microsoft's DDF v2 definitions into typed LCRUD operations with OMA-DM SyncML — the Configuration Service Provider surface, callable like any other Go package.

**AI agents that can use Windows.**
[windows-mcp-server](https://github.com/deploymenttheory/windows-mcp-server) bridges agents to the desktop through the Windows accessibility tree: UI automation, synthetic input, window control, PowerShell, registry, filesystem. No vision model in the loop.

---

## Config as Code — Terraform

Manage your modern workplace estate as version-controlled, peer-reviewed, pipeline-deployed code.

| Repository | Reach for it when | Status |
|---|---|:--:|
| **[terraform-provider-jamfpro](https://github.com/deploymenttheory/terraform-provider-jamfpro)** | The community Jamf Pro tf provider for classic and Jamf Pro APIs | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[terraform-provider-microsoft365](https://github.com/deploymenttheory/terraform-provider-microsoft365)** | The community M365 tf provider for Graph v1.0 *and* beta APIs | ![](https://img.shields.io/badge/status-experimental-EAAA32) |
| **[terraform-provider-thousandeyes](https://github.com/deploymenttheory/terraform-provider-thousandeyes)** | You manage ThousandEyes network monitoring alongside the estate | ![](https://img.shields.io/badge/status-experimental-EAAA32) |
| **[terraform-plugin-framework-codegen](https://github.com/deploymenttheory/terraform-plugin-framework-codegen)** | You're building your own provider and want the boilerplate generated | ![](https://img.shields.io/badge/status-experimental-EAAA32) |

**Learn and copy:**
[terraform-training-jamfpro](https://github.com/deploymenttheory/terraform-training-jamfpro) — hands-on Terraform + GitOps course for workplace engineers ·
[terraform-demo-jamfpro-v2](https://github.com/deploymenttheory/terraform-demo-jamfpro-v2) — reference GitHub Actions + Terraform Cloud pipeline ·
[terraform-demo-microsoft365](https://github.com/deploymenttheory/terraform-demo-microsoft365) — reference GitLab branching + Terraform pipeline

## Go API SDKs

Typed, idiomatic clients for the tools that run the modern workplace — the layer the providers and CLIs are built on.

| Repository | Reach for it when | Status |
|---|---|:--:|
| **[go-sdk-jamfpro-v2](https://github.com/deploymenttheory/go-sdk-jamfpro-v2)** | You're writing Go against Jamf Pro and want the full API surface — 700+ functions | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-sdk-jamfprotect](https://github.com/deploymenttheory/go-sdk-jamfprotect)** | You're automating Jamf Protect endpoint security | ![](https://img.shields.io/badge/status-GA-3FB950) |
| **[go-sdk-appleservices](https://github.com/deploymenttheory/go-sdk-appleservices)** | You need Apple enterprise services — ABM, DDM, MDM, notarization, iTunes | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-sdk-sofa](https://github.com/deploymenttheory/go-sdk-sofa)** | You need to know what Apple shipped, when, and which CVEs it closed | ![](https://img.shields.io/badge/status-GA-3FB950) |
| **[go-sdk-thousandeyes](https://github.com/deploymenttheory/go-sdk-thousandeyes)** | You want the ThousandEyes v7 API with retries, throttling and pagination handled | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-sdk-workbrew](https://github.com/deploymenttheory/go-sdk-workbrew)** | You manage Homebrew across a fleet | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-sdk-nexthink](https://github.com/deploymenttheory/go-sdk-nexthink)** | You're pulling digital-experience telemetry into your own tooling | ![](https://img.shields.io/badge/status-experimental-EAAA32) |
| **[go-sdk-virustotal](https://github.com/deploymenttheory/go-sdk-virustotal)** | You're screening binaries or hashes before they reach the fleet | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-sdk-cve](https://github.com/deploymenttheory/go-sdk-cve)** | You need NVD CVE data in a vulnerability workflow | ![](https://img.shields.io/badge/status-experimental-EAAA32) |
| **[go-lib-winget-pkgs](https://github.com/deploymenttheory/go-lib-winget-pkgs)** | You want WinGet package metadata from a local clone, with no API calls | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-api-http-client](https://github.com/deploymenttheory/go-api-http-client)** | You're building your own workplace API client and want auth, retries and rate limiting solved | ![](https://img.shields.io/badge/status-preview-58A6FF) |

> [!NOTE]
> **go-sdk-jamfpro-v2 supersedes [go-api-sdk-jamfpro](https://github.com/deploymenttheory/go-api-sdk-jamfpro).** The original SDK is still the one most search results point at, but new work should start on v2 — wider coverage, and where ongoing development happens.

<sub>Also: [go-sdk-brew](https://github.com/deploymenttheory/go-sdk-brew) · [go-sdk-chocolatey](https://github.com/deploymenttheory/go-sdk-chocolatey) — package-manager SDKs.</sub>

## Platform bindings

Idiomatic Go generated from vendor metadata — the whole OS API surface, typed and callable. This is the foundation for building native Windows and macOS applications in Go, work that normally requires C, Swift or .NET.

| Repository | Reach for it when | Status |
|---|---|:--:|
| **[go-bindings-macosplatform](https://github.com/deploymenttheory/go-bindings-macosplatform)** | You need macOS frameworks from Go, over a purego/cgo Objective-C bridge | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-bindings-win32](https://github.com/deploymenttheory/go-bindings-win32)** | You need any Win32 API — every function, struct, enum and COM interface, from win32metadata | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-bindings-winrt](https://github.com/deploymenttheory/go-bindings-winrt)** | You need modern Windows features — toasts, Bluetooth LE, Windows Hello, MDM/provisioning | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-bindings-wmi](https://github.com/deploymenttheory/go-bindings-wmi)** | You want typed WMI / CIM classes instead of hand-rolled COM plumbing | ![](https://img.shields.io/badge/status-GA-3FB950) |
| **[go-bindings-wdk](https://github.com/deploymenttheory/go-bindings-wdk)** | You're working against the Windows Driver Kit surface (`Windows.Wdk.*`) | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-bindings-windowsappsdk](https://github.com/deploymenttheory/go-bindings-windowsappsdk)** | You're building a modern Windows desktop app in Go | ![](https://img.shields.io/badge/status-experimental-EAAA32) |
| **[go-winmd](https://github.com/deploymenttheory/go-winmd)** | You're generating your own bindings — this is the shared metadata parser underneath all of the above | ![](https://img.shields.io/badge/status-preview-58A6FF) |

## Systems & OS-level tooling

Where the bindings get used: filesystems, firmware, provisioning and install media.

| Repository | Reach for it when | Status |
|---|---|:--:|
| **[go-apfs-v2](https://github.com/deploymenttheory/go-apfs-v2)** | You need to read, mount or write APFS and HFS+ volumes without macOS | ![](https://img.shields.io/badge/status-GA-3FB950) |
| **[go-sdk-vtpm2](https://github.com/deploymenttheory/go-sdk-vtpm2)** | You need a software TPM 2.0 for measured boot, BitLocker sealing or attestation | ![](https://img.shields.io/badge/status-GA-3FB950) |
| **[go-sdk-winmediafoundry](https://github.com/deploymenttheory/go-sdk-winmediafoundry)** | You're acquiring or building Windows install media in a pipeline | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-sdk-windowscsp](https://github.com/deploymenttheory/go-sdk-windowscsp)** | You need typed Configuration Service Provider operations with OMA-DM SyncML | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-macos-sandbox](https://github.com/deploymenttheory/go-macos-sandbox)** | You need to run or inspect code under the macOS sandbox | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-appdeploymenttoolkit](https://github.com/deploymenttheory/go-appdeploymenttoolkit)** | You want PSADT-style app deployment without a PowerShell dependency | ![](https://img.shields.io/badge/status-experimental-EAAA32) |
| **[go-settings-catalog](https://github.com/deploymenttheory/go-settings-catalog)** | You're working with the Intune settings catalog programmatically | ![](https://img.shields.io/badge/status-experimental-EAAA32) |

## AI & agents

| Repository | Reach for it when | Status |
|---|---|:--:|
| **[windows-mcp-server](https://github.com/deploymenttheory/windows-mcp-server)** | You want an AI agent to drive Windows through the accessibility tree — UI automation, input, registry, PowerShell, no vision model | ![](https://img.shields.io/badge/status-experimental-EAAA32) |

<details>
<summary><b>Everything else</b> — utilities, and superseded projects kept for reference</summary>

<br/>

**Utilities**

- [go-jamf-guid-sharder](https://github.com/deploymenttheory/go-jamf-guid-sharder) — shard Jamf Pro GUID lists by rule, ready for deployment groups
- [go-jamf-service-status](https://github.com/deploymenttheory/go-jamf-service-status) — Jamf service status checks
- [macos-autopkg-factory](https://github.com/deploymenttheory/macos-autopkg-factory) — AutoPkg orchestration for macOS packaging
- [workplace-devtools-jamfpro](https://github.com/deploymenttheory/workplace-devtools-jamfpro) — assorted Jamf Pro developer tooling
- [go-api-http-client-integrations](https://github.com/deploymenttheory/go-api-http-client-integrations) — auth integrations for `go-api-http-client`

**Superseded — start on the newer project instead**

- [go-api-sdk-jamfpro](https://github.com/deploymenttheory/go-api-sdk-jamfpro) → **[go-sdk-jamfpro-v2](https://github.com/deploymenttheory/go-sdk-jamfpro-v2)**
- [go-apfs](https://github.com/deploymenttheory/go-apfs) → **[go-apfs-v2](https://github.com/deploymenttheory/go-apfs-v2)**
- [terraform-demo-jamfpro](https://github.com/deploymenttheory/terraform-demo-jamfpro) → **[terraform-demo-jamfpro-v2](https://github.com/deploymenttheory/terraform-demo-jamfpro-v2)**
- [terraform-importer-jamfpro](https://github.com/deploymenttheory/terraform-importer-jamfpro), [jamftf-python-terraform-importer](https://github.com/deploymenttheory/jamftf-python-terraform-importer) — earlier import tooling
- [go-api-sdk-mitrecve](https://github.com/deploymenttheory/go-api-sdk-mitrecve) → **[go-sdk-cve](https://github.com/deploymenttheory/go-sdk-cve)**

</details>

---

## Principles

- **Everything as code** — if it can be configured, it should be versioned, tested and automated
- **Generated from source of truth** — vendor metadata, not hand-transcribed docs that drift
- **Cross-platform by default** — macOS and Windows are first-class, never afterthoughts
- **Built in the open** — open source, community-first, no vendor gatekeeping

## Community & contributing

Built for the community, by the community. Mac admins, Windows endpoint engineers and DevOps practitioners all welcome.

- **Discord** — [join the community server](https://discord.gg/Uq8zG6g7WE)
- **Slack** — [Mac Admins Slack](https://macadmins.slack.com/archives/C06R172PUV6), `#terraform-provider-jamfpro`
- **Discussions** — GitHub Discussions on each repository
- **Issues & PRs** — bug reports, feature requests and contributions welcome across every repo

---

*Made with ❤️ by the Deployment Theory community*
