# Frequently Asked Questions (FAQ)

Welcome to the OperationsPAI FAQ. If you don't find your answer here, please join our [GitHub Discussions](https://github.com/OperationsPAI/operationspai.github.io/discussions).

## General Questions

### What is OperationsPAI?
OperationsPAI is an open-source community building a self-evolving training environment for Root Cause Analysis (RCA) in microservices. It bridges the gap between academic research and industrial practice.

### How is this different from Chaos Mesh or Litmus?
While those tools focus on manual fault injection, OperationsPAI uses **intelligent fault scheduling** (via Pandora) to evolve failure scenarios based on how well your algorithms perform.

### What are the core values of this project?
Our community is guided by eight core principles, including being **Open by Default**, prioritizing **Community First**, and valuing **Quality Over Speed**.

## Technical & Installation

### What technologies does OperationsPAI use?
The ecosystem is built using **Go, Python, and Java**, running on **Kubernetes** with **OpenTelemetry** for observability.

### Where can I find the Technical Architecture?
A high-level overview is available in our [Technical Architecture documentation](https://operationspai.github.io/architecture).

### How do I report a bug?
Please use our [Bug Report Template](https://github.com/OperationsPAI/operationspai.github.io/blob/main/.github/ISSUE_TEMPLATE/bug_report.md) and include your OS, Kubernetes version, and relevant logs.

## Contributing

### How can I become a contributor?
Start by reading our [Contributing Guide](CONTRIBUTING.md). We recommend first-time contributors look for issues labeled `good-first-issue`.

### What is the "Contributor Ladder"?
We recognize community members through various roles: **Contributor, Active Contributor, Reviewer, Maintainer, and Core Team**. Progression is based on sustained merit and expertise.

### How are decisions made in the project?
During our current **Bootstrap Phase**, day-to-day decisions are made by repository maintainers, while strategic decisions are led by the Core Team with community input.

## Research & Academic

### How should I cite OperationsPAI in my research?
We are currently finalizing our official citation format. In the meantime, please link to our [official website](https://operationspai.github.io).

### Can I contribute my own RCA algorithms?
Yes! We encourage researchers to add their algorithms to the platform for standardized evaluation. Check the [RCABench Platform](https://github.com/OperationsPAI/rcabench-platform) for integration details.