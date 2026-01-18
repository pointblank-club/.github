# Google Summer of Code 2026 - Project Ideas

Welcome to the pointblank-club GSoC 2026 ideas page. This document consolidates project ideas across all our repositories for prospective GSoC contributors.

## About pointblank-club

pointblank-club is an organization focused on systems programming, security tools, and compiler optimization. Our projects span container runtimes, binary analysis, system hardening, and machine learning for compilers.

## How to Get Started

1. **Explore our repositories** - Familiarize yourself with the projects that interest you
2. **Read the documentation** - Each repository has a README and CONTRIBUTING.md
3. **Join the community** - Participate in GitHub Discussions and Issues
4. **Start small** - Look for `good first issue` labels to make initial contributions
5. **Reach out to mentors** - Discuss your ideas and get feedback early

## Project Ideas

---

### kettle: Add Container Lifecycle Management and Kubernetes Support

**Repository:** [pointblank-club/kettle](https://github.com/pointblank-club/kettle)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/kettle/blob/main/GSOC-2026.md)

#### Summary

Extend kettle with full container lifecycle management (create, start, stop, delete) and add Kubernetes integration to run and manage containers as pods.

#### Description

This project focuses on evolving kettle from a minimal runtime engine into a usable container runtime with clear lifecycle primitives and basic Kubernetes compatibility. The work includes wiring lifecycle on top of low-level runtimes, integrating with OCI concepts, and adding a Kubernetes-facing layer to manage containers through standard tooling.

#### Details

| Attribute | Value |
|-----------|-------|
| Skill level | Intermediate |
| Language | Go |
| Expected size | Medium |
| Mentors | Rahul K ([@rahulk789](https://github.com/rahulk789), rahul.u.india[at]gmail[.]com) |

#### Relevant Links

- [containerd](https://github.com/containerd/containerd)
- [runc](https://github.com/opencontainers/runc)

---

### vestigo: Automated Peripheral Modeling

**Repository:** [pointblank-club/vestigo](https://github.com/pointblank-club/vestigo)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/vestigo/blob/main/GSOC-2026.md)

#### Summary

Automatically detect and handle missing hardware peripherals (NVRAM, GPIO, Watchdogs) to prevent IoT firmware crashes during dynamic analysis.

#### Description

This project focuses on increasing the "Success Rate" of emulation by building a "Peripheral Stubber" that intercepts invalid memory accesses in Qiling and provides mock data to keep the firmware running.

#### Details

| Attribute | Value |
|-----------|-------|
| Skill level | Intermediate |
| Languages | Python, Assembly (ARM/MIPS) |
| Expected size | Large (350 hours) |
| Mentors | Kamini Banait ([@kamini08](https://github.com/kamini08), kaminibanait03[at]gmail[.]com) |

#### Relevant Links

- [Qiling Documentation](https://docs.qiling.io/en/latest/)
- [Unicorn Engine](https://unicorn-engine.org/)

---

### vestigo: Cross-Modal Dynamic Instrumentation (Static-to-Dynamic Bridge)

**Repository:** [pointblank-club/vestigo](https://github.com/pointblank-club/vestigo)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/vestigo/blob/main/GSOC-2026.md)

#### Summary

Translate Static Analysis findings from Ghidra into Dynamic Instrumentation scripts for Frida/Qiling to automatically verify cryptographic functions.

#### Description

This project focuses on closing the loop between "Guessing" and "Proving" by writing a generator that takes Ghidra's predicted function addresses (e.g., "Potential AES at 0x4000") and auto-generates Frida hooks to intercept those specific addresses. It also includes developing a Real-Time Entropy Monitor that scans memory buffers during execution to distinguish between high-entropy ciphertext and low-entropy keys/plaintext.

#### Details

| Attribute | Value |
|-----------|-------|
| Skill level | Intermediate |
| Languages | Python, JavaScript (Frida), Java (Ghidra) |
| Expected size | Medium (175 hours) |
| Mentors | Kamini Banait ([@kamini08](https://github.com/kamini08), kaminibanait03[at]gmail[.]com) |

#### Relevant Links

- [Frida Documentation](https://frida.re/docs/home/)
- [Ghidra](https://ghidra-sre.org/)

---

### vestigo: Differential Trace Analysis & Taint Tracking

**Repository:** [pointblank-club/vestigo](https://github.com/pointblank-club/vestigo)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/vestigo/blob/main/GSOC-2026.md)

#### Summary

Compare execution traces of the same binary under different inputs to isolate cryptographic processing logic without needing symbol names.

#### Description

This project focuses on "Behavioral Identification" by building a tracer on top of Qiling that records memory access patterns and instruction sequences. By running the binary twice with slightly different inputs (e.g., changing 1 bit), implement algorithms to detect the "Avalanche Effect" in the execution trace, effectively pinpointing the exact basic blocks responsible for encryption/hashing.

#### Details

| Attribute | Value |
|-----------|-------|
| Skill level | Intermediate |
| Languages | Python, C++ |
| Expected size | Large (350 hours) |
| Mentors | Kamini Banait ([@kamini08](https://github.com/kamini08), kaminibanait03[at]gmail[.]com) |

#### Relevant Links

- [Avalanche Effect](https://en.wikipedia.org/wiki/Avalanche_effect)
- [Qiling Taint Analysis Wiki](https://github.com/qilingframework/qiling/wiki/Taint-Analysis)

---

### oaas: Windows PE Binary-to-Binary Obfuscation Pipeline

**Repository:** [pointblank-club/oaas](https://github.com/pointblank-club/oaas)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/oaas/blob/main/GSOC-2026.md)

#### Summary

Implement a working binary-to-binary obfuscation pipeline for Windows PE executables. The pipeline will lift binaries to LLVM IR, apply obfuscation passes, and recompile to an obfuscated PE binary.

#### Description

Currently oaas only supports source-to-binary obfuscation. This project enables obfuscating existing binaries where source code is unavailable - useful for legacy software protection, third-party library hardening, and security research. The pipeline uses Ghidra for CFG extraction, McSema/RetDec for lifting to LLVM IR, applies OLLVM passes, and recompiles back to a working PE.

#### Details

| Attribute | Value |
|-----------|-------|
| Skill level | Intermediate |
| Languages | Python, C++, Bash |
| Expected size | Medium (~175 hours) |
| Mentors | Akash Singh ([@SkySingh04](https://github.com/SkySingh04), akashsingh2210670[at]gmail[.]com) |

#### Relevant Links

- [McSema](https://github.com/lifting-bits/mcsema)
- [RetDec](https://github.com/avast/retdec)
- [Ghidra](https://ghidra-sre.org/)

---

### syshardn: Scheduled Compliance Scans and History

**Repository:** [pointblank-club/syshardn](https://github.com/pointblank-club/syshardn)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/syshardn/blob/main/GSOC-2026.md)

#### Summary

Extend syshardn with scheduled scan execution, persistent scan history storage, and artifact export. Integrate with OS schedulers (cron, systemd timers, Task Scheduler).

#### Details

| Attribute | Value |
|-----------|-------|
| Skill level | Intermediate |
| Language | Python |
| Expected size | Medium (~175 hours) |
| Mentors | R Aswin ([@Aswinr24](https://github.com/Aswinr24), aswinr242004[at]gmail[.]com) |

#### Relevant Links

- [systemd timers](https://www.freedesktop.org/software/systemd/man/systemd.timer.html)
- [cron](https://man7.org/linux/man-pages/man5/crontab.5.html)
- [Windows Task Scheduler](https://learn.microsoft.com/en-us/windows/win32/taskschd/task-scheduler-start-page)

---

### syshardn: macOS Platform Support

**Repository:** [pointblank-club/syshardn](https://github.com/pointblank-club/syshardn)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/syshardn/blob/main/GSOC-2026.md)

#### Summary

Add macOS support with platform detection, macOS executor (check/apply/rollback), and a focused macOS rule pack covering password policy, screen lock, firewall, and FileVault.

#### Details

| Attribute | Value |
|-----------|-------|
| Skill level | Intermediate |
| Language | Python |
| Expected size | Small (~90 hours) |
| Prerequisites | Access to macOS; familiarity with macOS security tools |
| Mentors | R Aswin ([@Aswinr24](https://github.com/Aswinr24), aswinr242004[at]gmail[.]com) |

#### Relevant Links

- [CIS Benchmarks for macOS](https://www.cisecurity.org/benchmark/apple_os)

---

### IRis: Graph Neural Networks (GNN) for Structure-Aware LLVM IR Analysis

**Repository:** [pointblank-club/IRis](https://github.com/pointblank-club/IRis)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/IRIS/blob/main/GSOC-2026.md)

#### Summary

Enhance the IRis optimization pipeline by integrating Graph Neural Networks (GNNs) to capture the structural and semantic relationships within LLVM IR, overcoming the limitations of static scalar feature vectors.

#### Description

IRis currently relies on static scalar metrics (e.g., instruction counts, loop depths) which discard critical structural information like control flow and data dependencies. This can lead to structurally distinct programs yielding identical feature vectors, confusing the predictive model and limiting optimization performance. This project aims to develop a robust pipeline to parse LLVM IR (.ll files) and construct representative graphs with nodes for Basic Blocks or individual instructions and edges for Control Flow Graph (CFG) and Data Flow Graph (DFG) connections. A GNN Encoder will be architected and integrated into the existing PassFormer model to process these graphs and generate structure-aware embedding vectors, serving as rich inputs for the Transformer Decoder to predict optimal pass sequences. The GNN-enhanced model will be trained and evaluated against the scalar-based baseline to demonstrate improved generalization on unseen programs and validate superior optimization metrics (execution time/binary size reduction) on the RISC-V target.

#### Details

| Attribute | Value |
|-----------|-------|
| Skill level | Intermediate |
| Languages | Python, PyTorch (Deep Learning), Graph Neural Networks (PyTorch Geometric/DGL), Compiler Theory (LLVM IR structure) |
| Expected size | 350 hours |
| Mentors | Shubhang ([@Zrahay](https://github.com/Zrahay), shubhangsinha44[at]gmail[.]com), Inchara ([@Incharajayaram](https://github.com/Incharajayaram), incharajayaram2020[at]gmail[.]com), Yash ([@YashSuthar983](https://github.com/YashSuthar983), yashsuthar983[at]gmail[.]com) |

---

### edgeFlow: Add RISC-V and WebAssembly Backend Support

**Repository:** [pointblank-club/edgeFlow](https://github.com/pointblank-club/edgeFlow)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/edgeFlow/blob/main/GSOC-2026.md)

#### Summary

Expand the compiler's code generation capabilities to support open hardware and web-based environments.

#### Description

This project focuses on writing new backend modules for the EdgeFlow compiler by translating the Intermediate Representation (IR) into compatible C++ code for RISC-V embedded targets and WebAssembly (WASM) modules, enabling browser-based inference and simulation.

#### Details

| Attribute | Value |
|-----------|-------|
| Skill level | Intermediate |
| Language | C++ |
| Expected size | Medium (175 hours) |
| Mentors | Kamini Banait ([@kamini08](https://github.com/kamini08), kaminibanait03[at]gmail[.]com) |

#### Relevant Links

- [RISC-V Technical Specifications](https://riscv.org/technical/specifications/)
- [WebAssembly C and C++](https://webassembly.org/docs/c-and-c++/)

---

### edgeFlow: Implement Language Server Protocol (LSP) Support

**Repository:** [pointblank-club/edgeFlow](https://github.com/pointblank-club/edgeFlow)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/edgeFlow/blob/main/GSOC-2026.md)

#### Summary

Develop a dedicated Language Server to provide a modern developer experience for the EdgeFlow DSL.

#### Description

This project focuses on building developer tooling to reduce configuration errors by implementing the LSP specification to provide real-time syntax highlighting, code completion, and semantic diagnostics (e.g., detecting hardware mismatches), packaged within a VS Code extension.

#### Details

| Attribute | Value |
|-----------|-------|
| Skill level | Intermediate |
| Languages | TypeScript, Python/C++ |
| Expected size | Medium (175 hours) |
| Mentors | Kamini Banait ([@kamini08](https://github.com/kamini08), kaminibanait03[at]gmail[.]com) |

#### Relevant Links

- [Language Server Protocol](https://microsoft.github.io/language-server-protocol/)
- [VS Code Language Server Extension Guide](https://code.visualstudio.com/api/language-extensions/language-server-extension-guide)

---

### edgeFlow: Implement Advanced IR Optimization Passes

**Repository:** [pointblank-club/edgeFlow](https://github.com/pointblank-club/edgeFlow)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/edgeFlow/blob/main/GSOC-2026.md)

#### Summary

Harden the compiler by implementing standard optimization algorithms within the Intermediate Representation (IR).

#### Description

This project focuses on improving the efficiency of the generated binary code by implementing graph-based algorithms for Dead Code Elimination (DCE), Common Subexpression Elimination (CSE), and Constant Folding to minimize model size and execution overhead.

#### Details

| Attribute | Value |
|-----------|-------|
| Skill level | Intermediate |
| Language | C++ |
| Expected size | Large (350 hours) |
| Mentors | Madhur Kumar ([@MadhurKumar004](https://github.com/MadhurKumar004), madhurkumar004[at]gmail[.]com) |

#### Relevant Links

- [LLVM Optimization Passes](https://llvm.org/docs/Passes.html)
- [Control-flow Graph](https://en.wikipedia.org/wiki/Control-flow_graph)

---

## General Information for Applicants

### Application Tips

- Start contributing early - familiarity with the codebase strengthens your application
- Propose realistic timelines based on the expected project size
- Demonstrate understanding of the technical challenges involved
- Show how your background prepares you for the project
- Be specific about deliverables and milestones

### Mentor Contact

For questions about specific projects, reach out via:

- Email: <admin@pointblank.club>
- GitHub Issues in the relevant repository
- GitHub Discussions (where available)
- Direct mentor contact (listed in project details)

---

## Contributing New Ideas

If you have a project idea that isn't listed here:

1. Open an issue in the relevant repository describing your idea
2. Include technical details, expected outcomes, and estimated scope
3. Discuss with maintainers to refine the proposal
4. If accepted, it may be added to this list

---

We look forward to working with GSoC 2026 contributors. Good luck with your applications!
