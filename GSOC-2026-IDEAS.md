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
| Mentors | Rahul K (rahul.u.india[at]gmail[.]com) |

#### Relevant Links

- [containerd](https://github.com/containerd/containerd)
- [runc](https://github.com/opencontainers/runc)

---

### vestigo: Automated Peripheral Modeling

**Repository:** [pointblank-club/vestigo](https://github.com/pointblank-club/vestigo)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/vestigo/blob/main/GSOC-2026.md)

Vestigo is a firmware analysis and crypto-detection pipeline built with Python. Potential GSoC project areas include:

- Expanding firmware format support
- Improving ML-based crypto detection accuracy
- Adding new analysis backends (Ghidra, Binary Ninja integration)
- Building a web-based analysis dashboard

Interested contributors should explore the repository and open a discussion to propose specific project ideas.

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
| Mentors | TBD |

#### Relevant Links

- [McSema](https://github.com/lifting-bits/mcsema)
- [RetDec](https://github.com/avast/retdec)
- [Ghidra](https://ghidra-sre.org/)

---

### syshardn: Ideas Coming Soon

**Repository:** [pointblank-club/syshardn](https://github.com/pointblank-club/syshardn)

syshardn is a multi-platform system hardening tool supporting Linux and Windows. Potential GSoC project areas include:

- Expanding hardening rule coverage
- Adding macOS support
- Building a configuration management interface
- Compliance reporting (CIS benchmarks, STIG)

Interested contributors should explore the repository and open a discussion to propose specific project ideas.

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
| Mentors | Shubhang, Inchara, Yash |


---

### edgeFlow: Implement Advanced IR Optimization Passes

**Repository:** [pointblank-club/edgeFlow](https://github.com/pointblank-club/edgeFlow)

**Full proposal:** [GSOC-2026.md](https://github.com/pointblank-club/edgeFlow/blob/main/GSOC-2026.md)

edgeFlow is a DSL for optimizing ML models on edge devices. Potential GSoC project areas include:

- Expanding hardware backend support
- New optimization passes for edge deployment
- Quantization and pruning improvements
- Integration with popular ML frameworks

Interested contributors should explore the repository and open a discussion to propose specific project ideas.

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
- Email: admin@pointblank.club
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
