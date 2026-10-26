# Deployment Theory

### the Modern Workplace rebuilt on go(lang).

Open-source building blocks for the modern workplace — **from the Terraform plan all the way down to the Win32 syscall.**

`Terraform` · `macOS` · `Windows` · `Device Management` · `Microsoft 365` · `Entra ID`

> **Who it's for** — Workplace and EUC platform teams who want to manage devices the way software teams ship code: versioned, tested, reviewed and automated.

We started with Terraform providers for Jamf Pro and Microsoft 365. Today we're provide full-stack Go tools, libraries and bindings for endpoint management, covering every layer between your pipeline and the operating system.

---

## Why Go

Device management has historically been written in whatever language the vendor shipped an SDK in (if one even exists). PowerShell here, Bash there, Swift or .Net when you need to touch the OS. This fragments tooling, testing and hiring. We have picked one language and stuck with it for every project.

- **One static binary, covers every platform.** Cross-compile from CI, ship a single artifact to macOS, Windows and Linux. No runtime, no interpreter, no dependency chain on the endpoint.

---

**Status labels** used throughout:
![](https://img.shields.io/badge/status-GA-3FB950) production-ready, stable API &nbsp;·&nbsp;
![](https://img.shields.io/badge/status-preview-58A6FF) usable now, API may still move &nbsp;·&nbsp;
![](https://img.shields.io/badge/status-experimental-EAAA32) early, spec-complete or lightly exercised

---

## Config as Code — Terraform

Manage your modern workplace estate as version-controlled, peer-reviewed, pipeline-deployed code.

| Repository | Reach for it when | Status |
|---|---|:--:|
| **[terraform-provider-jamfpro](https://github.com/deploymenttheory/terraform-provider-jamfpro)** | The community Jamf Pro tf provider for classic and Jamf Pro APIs | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[terraform-provider-microsoft365](https://github.com/deploymenttheory/terraform-provider-microsoft365)** | The community M365 tf provider for Graph v1.0 *and* beta APIs | ![](https://img.shields.io/badge/status-experimental-EAAA32) |

**Learn and copy:**
[terraform-training-jamfpro](https://github.com/deploymenttheory/terraform-training-jamfpro) — hands-on Terraform + GitOps course for workplace engineers ·
[terraform-demo-jamfpro-v2](https://github.com/deploymenttheory/terraform-demo-jamfpro-v2) — reference GitHub Actions + Terraform Cloud pipeline ·
[terraform-demo-microsoft365](https://github.com/deploymenttheory/terraform-demo-microsoft365) — reference GitLab branching + Terraform pipeline

## Go API SDKs

Typed, idiomatic clients for the tools that run the modern workplace — the layer the providers and CLIs are built on.

| Repository | Reach for it when | Status |
|---|---|:--:|
| **[go-sdk-jamfpro-v2](https://github.com/deploymenttheory/go-sdk-jamfpro-v2)** | You're writing Go against Jamf Pro and want the full API surface — 700+ functions | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-sdk-appleservices](https://github.com/deploymenttheory/go-sdk-appleservices)** | You need Apple enterprise services — ABM, DDM, MDM, notarization, iTunes | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-sdk-sofa](https://github.com/deploymenttheory/go-sdk-sofa)** | You need to know what Apple shipped, when, and which CVEs it closed | ![](https://img.shields.io/badge/status-GA-3FB950) |
| **[go-sdk-thousandeyes](https://github.com/deploymenttheory/go-sdk-thousandeyes)** | You want the ThousandEyes v7 API with retries, throttling and pagination handled | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-sdk-workbrew](https://github.com/deploymenttheory/go-sdk-workbrew)** | You manage Homebrew across a fleet | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-sdk-nexthink](https://github.com/deploymenttheory/go-sdk-nexthink)** | You're pulling digital-experience telemetry into your own tooling | ![](https://img.shields.io/badge/status-experimental-EAAA32) |
| **[go-sdk-virustotal](https://github.com/deploymenttheory/go-sdk-virustotal)** | You're screening binaries or hashes before they reach the fleet | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-lib-winget-pkgs](https://github.com/deploymenttheory/go-lib-winget-pkgs)** | You want WinGet package metadata from a local clone, with no API calls | ![](https://img.shields.io/badge/status-preview-58A6FF) |

## Platform bindings

Idiomatic Go generated from vendor metadata — the whole OS API surface, typed and callable. This is the foundation for building native Windows and macOS applications in Go, work that normally requires C, Swift or .NET.

| Repository | Reach for it when | Status |
|---|---|:--:|
| **[go-bindings-macosplatform](https://github.com/deploymenttheory/go-bindings-macosplatform)** | You need macOS frameworks from Go, over a purego/cgo Objective-C bridge | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-bindings-win32](https://github.com/deploymenttheory/go-bindings-win32)** | You need any Win32 API — every function, struct, enum and COM interface, from win32metadata | ![](https://img.shields.io/badge/status-GA-3FB950) |
| **[go-bindings-winrt](https://github.com/deploymenttheory/go-bindings-winrt)** | You need modern Windows features — toasts, Bluetooth LE, Windows Hello, MDM/provisioning | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-bindings-wmi](https://github.com/deploymenttheory/go-bindings-wmi)** | You want typed WMI / CIM classes instead of hand-rolled COM plumbing | ![](https://img.shields.io/badge/status-GA-3FB950) |
| **[go-bindings-wdk](https://github.com/deploymenttheory/go-bindings-wdk)** | You're working against the Windows Driver Kit surface (`Windows.Wdk.*`) | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-bindings-windowsappsdk](https://github.com/deploymenttheory/go-bindings-windowsappsdk)** | You're building a modern Windows desktop app in Go | ![](https://img.shields.io/badge/status-preview-58A6FF) |
| **[go-winmd](https://github.com/deploymenttheory/go-winmd)** | You're generating your own bindings — this is the shared metadata parser underneath all of the above | ![](https://img.shields.io/badge/status-GA-3FB950) |

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

---

## Principles

- **Everything as code** : if it can be configured, it should be versioned, tested and automated
- **Generated from source of truth** : vendor metadata, not hand-transcribed docs that drift
- **Cross-platform by default** : macOS and Windows parity by design, never as an afterthought
- **Built in the open** : open source, community-first, minimal vendor gatekeeping

## Community & contributing

Built for the community, by the community. Mac admins, Windows endpoint engineers and DevOps practitioners all welcome.

- **Discord** — [join the community server](https://discord.gg/Uq8zG6g7WE)
- **Slack** — [Mac Admins Slack](https://macadmins.slack.com/archives/C06R172PUV6), `#terraform-provider-jamfpro`
- **Discussions** — GitHub Discussions on each repository
- **Issues & PRs** — bug reports, feature requests and contributions welcome across every repo

---

*Made with ❤️ by the Deployment Theory team*
