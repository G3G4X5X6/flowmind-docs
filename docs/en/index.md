---
layout: home

hero:
  name: FlowMind
  text: AI-Native Application Security Platform
  tagline: An integrated security workbench combining MITM proxy, traffic analysis, fuzzing, security scanning, and AI reasoning
  image:
    src: /logo.svg
    alt: FlowMind
  actions:
    - theme: brand
      text: Get Started
      link: /en/guide/getting-started
    - theme: alt
      text: User Guide
      link: /en/guide/
    - theme: alt
      text: GitHub
      link: https://github.com/G3G4X5X6/flowmind-docs

features:
  - icon: 🔍
    title: Smart Proxy Capture
    details: Built-in Rust MITM engine with real-time HTTP/HTTPS/WebSocket capture, automatic CA certificate management, and detailed traffic inspection
  - icon: 🔄
    title: Traffic Forwarding & Interception
    details: Real-time forwarder list, request detail panel, Hold/Modify/Drop interception control for precise request handling
  - icon: 🎯
    title: Request Replay & Fuzzing
    details: Support for raw request replay, structured editing, and multi-strategy fuzzing (IDOR/Auth Strip/Header wordlists)
  - icon: 🛡️
    title: Security Scanning Engine
    details: 28 passive rules + 8 active rules with Rhai scripting for custom rules and hot reload, automatically detects sensitive info, injection attacks, and config flaws
  - icon: 🤖
    title: AI Security Analysis
    details: Multi-provider chat, tool calling, MCP, Skills, smart replay and fuzz assistance
  - icon: 📊
    title: Project Management & Reports
    details: Project isolation, clipping, HTML/JSON/PDF report export
---

<style>
:root {
  --vp-home-hero-name-color: transparent;
  --vp-home-hero-name-background: -webkit-linear-gradient(120deg, #6366f1 30%, #06b6d4);
}
</style>


![FlowMind Home](/screenshots/首页.png)

## Why Choose FlowMind?

### 🚀 High Performance

Built-in Rust-based proxy engine with no external dependencies. Virtual list technology ensures smooth browsing of massive traffic data.

### 🔒 Secure & Reliable

All data stays local by default. What you send to external LLMs or MCP servers depends on your AI settings.

### 🧠 AI-Native

Deep AI integration: providers, tools, MCP, Skills, and Engram memory across replay and fuzz workflows.

### 🔌 Extensible

Support for Rhai scripts and declarative YAML plugin mechanisms to easily extend scanning rules for customized needs.

## Community

- [GitHub Issues](https://github.com/G3G4X5X6/flowmind-docs/issues) - Report product issues and suggestions
- [Docs Issues](https://github.com/G3G4X5X6/flowmind-docs/issues) - Report documentation issues
- [Contributing Guide](./dev/contributing.md) - Contribute to documentation
