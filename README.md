[README.md](https://github.com/user-attachments/files/30874689/README.md)
<p align="center">
  <img src="logo.png" alt="TraceLinter Logo" width="180"/>
</p>

<h1 align="center">TraceLinter Enterprise 🛡️⚡</h1>

<p align="center">
  <b>Static Code Analysis (Roslyn AST) + OpenTelemetry (OTLP) + AI-Powered Refactoring.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/.NET-9.0-512BD4?style=for-the-badge&logo=dotnet" alt=".NET 9" />
  <img src="https://img.shields.io/badge/C%23-13.0-239120?style=for-the-badge&logo=csharp" alt="C#" />
  <img src="https://img.shields.io/badge/WPF-Windows-0078D4?style=for-the-badge&logo=windows" alt="WPF" />
  <img src="https://img.shields.io/badge/License-Enterprise-success?style=for-the-badge" alt="License" />
</p>

---

## 📌 Overview

**TraceLinter Enterprise** bridges the gap between **Static Code Analysis** (Roslyn AST) and **Runtime Telemetry** (OpenTelemetry OTLP). Instead of warning about theoretical code smells, TraceLinter identifies performance bottlenecks that actually impact production based on real execution metrics (RPM, P95 Latency).

It enables automated code refactoring using Artificial Intelligence (supporting 100% local models via **Ollama**, as well as **Google Gemini** and **OpenAI GPT-4o**), automatically preserving safety via `.bak` backups.

---

## ✨ Key Features

- 🔍 **Roslyn AST Static Analysis:** Scans C# codebases to detect loops, method signatures, complexity, and exact line locations.
- 📊 **OpenTelemetry (OTLP) Ingestion:** Processes OTLP JSON telemetry with Requests Per Minute (RPM) and P95 Latency metrics.
- ⚙️ **Configurable Thresholds:** Custom dynamic thresholds for Minimum Traffic (RPM) and Latency (ms) at runtime.
- 🤖 **Multi-Provider AI Refactoring:** Built-in integrations for Ollama (Local `llama3`), Gemini, and OpenAI.
- 🛠️ **1-Click Automated Refactor:** Directly replaces inefficient code in original source files with automatic `.bak` backups.
- 🌐 **Bilingual UI & Exporters:** Native English and Spanish UI support with 1-click export to HTML and Markdown reports.
- 🧪 **Unit Tested:** Built with xUnit ensuring high stability for risk evaluation and analyzer modules.

---

## 🏗️ Solution Architecture

```text
TraceLinter/
├── TraceLinter.Core/                   # Core Models and Interfaces
├── TraceLinter.Analysis.Roslyn/        # C# AST Parsing via Microsoft.CodeAnalysis.CSharp
├── TraceLinter.Telemetry.OpenTelemetry/# OTLP JSON Telemetry Ingestor
├── TraceLinter.Engine/                 # Risk Evaluation Engine & LLM Integrations
├── TraceLinter.Desktop/                # WPF Desktop User Interface (.NET 9)
└── TraceLinter.Tests/                  # xUnit Test Suite

📜 License and Terms of Use
This project is proprietary software distributed under a commercial enterprise license.

✅ Licensed Use: Access, execution, and updates require a valid commercial license key obtained through official channels (Lemon Squeezy Store).

❌ Restrictions: Unauthorized distribution, modification, reverse engineering for redistribution, or commercial resale of this software (or parts of it) without an active enterprise license is strictly prohibited.
