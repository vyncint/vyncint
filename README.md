<div align="center">

# Vyncint Ng

**Rust systems developer · GPU tooling · terminal testing infrastructure · Kubernetes · Go**

Creator of [termlens](https://github.com/vyncint/termlens) &nbsp;·&nbsp; #2 contributor to [NVlabs/cuda-oxide](https://github.com/NVlabs/cuda-oxide) &nbsp;·&nbsp; #7 contributor to [kube-logging/logging-operator](https://github.com/kube-logging/logging-operator)

[![followers](https://img.shields.io/github/followers/vyncint?style=flat-square&logo=github&label=followers)](https://github.com/vyncint?tab=followers)
[![crates.io](https://img.shields.io/badge/crates.io-42%20published-orange?style=flat-square&logo=rust&logoColor=white)](https://crates.io/users/vyncint)
[![website](https://img.shields.io/badge/vyncint.me-website-blue?style=flat-square&logo=githubpages&logoColor=white)](https://vyncint.me)

![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white)
![CUDA](https://img.shields.io/badge/CUDA-76B900?style=flat-square&logo=nvidia&logoColor=white)
![PTX](https://img.shields.io/badge/PTX-76B900?style=flat-square)
![Metal](https://img.shields.io/badge/Metal-000000?style=flat-square&logo=apple&logoColor=white)
![Apache Arrow](https://img.shields.io/badge/Apache_Arrow-1F1F1F?style=flat-square&logo=apachearrow)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Swift](https://img.shields.io/badge/Swift-F05138?style=flat-square&logo=swift&logoColor=white)

</div>

I build Rust tools for testing terminal applications and analysing GPU kernels,
and I work on Kubernetes operators and sandboxed agent runtimes. Most of my
contributions are testing infrastructure and CI: making a tool's claims
checkable, and catching the places where its documentation and its code
disagree.

## Projects

Six Rust products on crates.io. termlens tests the other five end to end: it runs
each real binary in a pseudo-terminal and asserts on the rendered screen.

| Project | | Version | Downloads |
| :-- | :-- | :-- | :-- |
| **[termlens](https://github.com/vyncint/termlens)** | Headless end-to-end testing for CLI and TUI apps: real PTYs, rendered-screen assertions, snapshots, screen diffs. The end-to-end example in Ratatui's [snapshot-testing recipe](https://ratatui.rs/recipes/testing/snapshots/). | [![v](https://img.shields.io/crates/v/termlens?style=flat-square&label=)](https://crates.io/crates/termlens) | ![d](https://img.shields.io/crates/d/termlens?style=flat-square&label=) |
| **[reconverge](https://github.com/vyncint/reconverge)** | Static analysis for Rust GPU kernels: divergent barriers and warp-collective hazards, explained lane by lane. No GPU required. | [![v](https://img.shields.io/crates/v/cargo-reconverge?style=flat-square&label=)](https://crates.io/crates/cargo-reconverge) | ![d](https://img.shields.io/crates/d/cargo-reconverge?style=flat-square&label=) |
| **[launchbound](https://github.com/vyncint/launchbound)** | Autotuning for GPU kernels: a convergence check per configuration, CUDA and Metal benchmarking, analytical estimates. | [![v](https://img.shields.io/crates/v/launchbound-cli?style=flat-square&label=)](https://crates.io/crates/launchbound-cli) | ![d](https://img.shields.io/crates/d/launchbound-cli?style=flat-square&label=) |
| **[oxmera](https://github.com/vyncint/oxmera)** | Tensor and deep-learning framework: autograd, CPU, Metal and CUDA backends, a terminal training dashboard. | [![v](https://img.shields.io/crates/v/oxmera?style=flat-square&label=)](https://crates.io/crates/oxmera) | ![d](https://img.shields.io/crates/d/oxmera?style=flat-square&label=) |
| **[oxidelake](https://github.com/vyncint/oxidelake)** | Arrow-native SQL engine on DataFusion or Ballista, with optional GPU acceleration and per-batch CPU fallback. | [![v](https://img.shields.io/crates/v/oxidelake-runtime?style=flat-square&label=)](https://crates.io/crates/oxidelake-runtime) | ![d](https://img.shields.io/crates/d/oxidelake-runtime?style=flat-square&label=) |
| **[mossaic](https://github.com/vyncint/mossaic)** | Plan, draw and track GitHub contribution art, with pixel-rendered graphs in the terminal. | [![v](https://img.shields.io/crates/v/mossaic?style=flat-square&label=)](https://crates.io/crates/mossaic) | ![d](https://img.shields.io/crates/d/mossaic?style=flat-square&label=) |

One Go project:

| Project | | Stars |
| :-- | :-- | :-- |
| **[openshell-driver-applecontainer](https://github.com/vyncint/openshell-driver-applecontainer)** | A compute driver for [NVIDIA OpenShell](https://github.com/NVIDIA/OpenShell) backed by [apple/container](https://github.com/apple/container): one micro-VM per sandbox on Apple silicon, roughly one second to Ready. | ![stars](https://img.shields.io/github/stars/vyncint/openshell-driver-applecontainer?style=flat-square&label=) |

## Upstream

| Project | | Contribution |
| :-- | :-- | :-- |
| **[NVlabs/cuda-oxide](https://github.com/NVlabs/cuda-oxide)** ![stars](https://img.shields.io/github/stars/NVlabs/cuda-oxide?style=flat-square&label=) | Rust-to-CUDA compiler | [165 merged pull requests](https://github.com/NVlabs/cuda-oxide/pulls?q=is%3Apr+is%3Amerged+author%3Avyncint), second of 48 [contributors](https://github.com/NVlabs/cuda-oxide/graphs/contributors). Mostly documentation that had drifted from the code and CI gates that could not fail, plus compiler fixes such as [carrying proved alignment through a field store](https://github.com/NVlabs/cuda-oxide/pull/795). |
| **[kube-logging/logging-operator](https://github.com/kube-logging/logging-operator)** ![stars](https://img.shields.io/github/stars/kube-logging/logging-operator?style=flat-square&label=) | Kubernetes logging operator | [33 merged pull requests](https://github.com/kube-logging/logging-operator/pulls?q=is%3Apr+is%3Amerged+author%3Avyncint), seventh of 149 [contributors](https://github.com/kube-logging/logging-operator/graphs/contributors). Rebuilt the end-to-end suite on [one shared harness](https://github.com/kube-logging/logging-operator/pull/2304) with [time-bounded kind calls](https://github.com/kube-logging/logging-operator/pull/2288); operator fixes for [dual-stack Fluent Bit metrics](https://github.com/kube-logging/logging-operator/pull/2273), [custom CAs on S3 outputs](https://github.com/kube-logging/logging-operator/pull/2272) and [dnsPolicy on the configcheck pod](https://github.com/kube-logging/logging-operator/pull/2285). |
| **[calfonso/rusternetes](https://github.com/calfonso/rusternetes)** ![stars](https://img.shields.io/github/stars/calfonso/rusternetes?style=flat-square&label=) | Kubernetes reimplemented in Rust | [10 merged pull requests](https://github.com/calfonso/rusternetes/pulls?q=is%3Apr+is%3Amerged+author%3Avyncint), fourth of 12 [contributors](https://github.com/calfonso/rusternetes/graphs/contributors). Correctness fixes across the control plane: [typed container-state timestamps](https://github.com/calfonso/rusternetes/pull/115), [negated field selectors on watch endpoints](https://github.com/calfonso/rusternetes/pull/99), [fractional and binary-SI resource quantities in the scheduler](https://github.com/calfonso/rusternetes/pull/87), [CronJob day-of-week numbering](https://github.com/calfonso/rusternetes/pull/111). |
| **[apple/containerization](https://github.com/apple/containerization)** ![stars](https://img.shields.io/github/stars/apple/containerization?style=flat-square&label=) | Linux containers on macOS | [Redact environment-variable values in `vminitd` debug logs](https://github.com/apple/containerization/pull/813); [consistent CIDR bounds for IPv4 and IPv6](https://github.com/apple/containerization/pull/827). |
| **[GoogleCloudPlatform/gcsfuse](https://github.com/GoogleCloudPlatform/gcsfuse)** ![stars](https://img.shields.io/github/stars/GoogleCloudPlatform/gcsfuse?style=flat-square&label=) | Cloud Storage as a file system | [Report a symlink's size as the length of its target](https://github.com/GoogleCloudPlatform/gcsfuse/pull/4943). |
| **[NVIDIA/OpenShell](https://github.com/NVIDIA/OpenShell)** ![stars](https://img.shields.io/github/stars/NVIDIA/OpenShell?style=flat-square&label=) | Runtime for autonomous agents | [Show persisted guidance on rejected policy chunks in the TUI](https://github.com/NVIDIA/OpenShell/pull/2908). |
| **[NVIDIA/NemoClaw](https://github.com/NVIDIA/NemoClaw)** ![stars](https://img.shields.io/github/stars/NVIDIA/NemoClaw?style=flat-square&label=) | Agents inside OpenShell | [Supply the Ultra template argument from the managed resolver](https://github.com/NVIDIA/NemoClaw/pull/7463). |

## How I work

| | |
| :-- | :-- |
| **Evidence over assertion** | A bug report states what was measured, against which released version. |
| **A check must be seen to fail** | Every new CI check is broken on purpose once, to prove it can fail, before it is trusted. |
| **Say what you did not do** | A pull request lists what it left out and why. A known gap is cheap; a false claim is expensive. |
| **AI-assisted, human-owned** | I use AI tools in development and take responsibility for reviewing, testing and maintaining the results. |

[More on how these projects are built](ENGINEERING.md) · [vyncint.me](https://vyncint.me)

## Contact

Open to collaboration on Rust tooling, GPU infrastructure, Kubernetes operators
and testing. Open an issue or discussion on any repository above.
