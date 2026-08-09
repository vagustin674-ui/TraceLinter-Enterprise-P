<p align="center">
  <img src="logo.png" alt="TraceLinter Logo" width="180"/>
</p>

<h1 align="center">TraceLinter Enterprise 🛡️⚡</h1>

<p align="center">
  <b>Static Code Analysis (Roslyn AST) + OpenTelemetry (OTLP) + AI-Powered Automated Refactoring & Enterprise Quality Gates.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/.NET-9.0-512BD4?style=for-the-badge&logo=dotnet" alt=".NET 9" />
  <img src="https://img.shields.io/badge/C%23-13.0-239120?style=for-the-badge&logo=csharp" alt="C#" />
  <img src="https://img.shields.io/badge/WPF-Windows-0078D4?style=for-the-badge&logo=windows" alt="WPF" />
  <img src="https://img.shields.io/badge/License-Enterprise-success?style=for-the-badge" alt="License" />
</p>

---

## 🎬 See TraceLinter in Action

<p align="center">
  <video src="./assets/TreceLinter Exp.mp4" width="100%" autoplay loop muted playsinline></video>
</p>

---

## 📌 Overview

**TraceLinter Enterprise** bridges the gap between **Static Code Analysis** (Roslyn AST) and **Runtime Telemetry** (OpenTelemetry OTLP). Instead of warning about theoretical code smells, TraceLinter identifies performance bottlenecks and vulnerabilities that actually impact production based on real execution metrics (RPM, P95 Latency). 

It enables automated code refactoring using Artificial Intelligence (supporting 100% local models via **Ollama**, as well as **Google Gemini** and **OpenAI GPT-4o**), automatically preserving safety via `.bak` backups and corporate Quality Gates.

---

## ✨ Key Features

- **🔍 Roslyn AST Static Analysis:** Scans C# codebases at the Abstract Syntax Tree level to detect code smells, heavy loops, critical `async void` methods, and hardcoded secrets (API Keys, JWT tokens).
- **📊 OpenTelemetry (OTLP) Ingestion:** Processes OTLP JSON telemetry, cross-referencing Requests Per Minute (RPM) and P95 Latency metrics directly with static code findings.
- **⚙️ Configurable Thresholds:** Custom dynamic thresholds for Minimum Traffic (RPM) and Latency (ms) at runtime.
- **🤖 Multi-Provider AI Refactoring:** Built-in native integrations for Ollama (Local `llama3`), Google Gemini, and OpenAI GPT-4o to generate automated optimizations and refactorings.
- **🛠️ 1-Click Automated Refactor:** Directly replaces inefficient code in original source files with automatic `.bak` backups and immediate re-analysis.
- **🚦 CI/CD Quality Gates & Exit Codes:** Command-line module (`TraceLinter.Cli`) capable of evaluating quality thresholds and returning exit codes (`Exit Code 1`) to block deployments or Pull Requests in GitHub Actions and Azure DevOps.
- **🛡️ Enterprise Compliance (SARIF & PDF/HTML):** Native export to industry standards like SARIF 2.1.0 (compatible with GitHub Code Scanning), interactive HTML reports, and executive documents.
- **🔐 Secure Licensing & Machine Locking:** License system protected via asymmetric cryptography (RSA 2048-bit) and local encrypted storage using Windows DPAPI, supporting environment variable activation in CI/CD environments.

---

## ❓ FAQ & Quickstart

### 1. How do I run my first audit in under 2 minutes?
1. Download and launch `TraceLinter.Desktop.exe`.
2. Select your C# project root folder (`C# Folder`).
3. Load your OTLP telemetry file (or use defaults) and click **Run Analysis** (`BtnRunAnalysis`). Instantly view the production impact dashboard!

### 2. How do I integrate TraceLinter into my GitHub Actions pipeline (CI/CD)?
Add this step to your `.github/workflows/tracelinter-ci.yml` file:
```yaml
- name: ⚡ Run TraceLinter CLI Audit
  run: dotnet run --project TraceLinter.Cli/TraceLinter.Cli.csproj -- --src ./ --sarif-out results.sarif
3. How do I configure custom rules for my enterprise?
Place a .tracelinter.json file in the root of your Git repository to define custom criticality thresholds and ignored directories (such as /migrations/ or /obj/) without manual setup.

🏗️ Solution Architecture
Plaintext
TraceLinter/
├── TraceLinter.Core/                 # Core Models and Interfaces
├── TraceLinter.Analysis.Roslyn/        # C# AST Parsing via Microsoft.CodeAnalysis.CSharp
├── TraceLinter.Telemetry.OpenTelemetry/# OTLP JSON Telemetry Ingestor
├── TraceLinter.Engine/               # Risk Evaluation Engine & LLM Integrations
├── TraceLinter.Desktop/              # WPF Desktop User Interface (.NET 9)
└── TraceLinter.Tests/                # xUnit Test Suite
📜 License and Terms of Use
This project is proprietary software distributed under a commercial enterprise license.

✅ Licensed Use: Access, execution, and updates require a valid commercial license key obtained through official channels (Lemon Squeezy Store).

❌ Restrictions: Unauthorized distribution, modification, reverse engineering for redistribution, or commercial resale of this software (or parts of it) without an active enterprise license is strictly prohibited.
