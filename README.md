# Kyverno AI Policy Assistant

This project showcases a **Kagent-powered AI assistant** that generates, explains, deploys and recommends [Kyverno](https://kyverno.io) policies from natural language descriptions or policy report violations. 

---

## Demo

**Watch the video walkthrough:** [[here](https://drive.google.com/file/d/1SyDGWR_dzvaIaby2VkaZxi9MxmJw-xGX/view)]

---

## Setup Instructions

### 1. Prerequisites

- Kubernetes cluster (e.g., KIND or Minikube)
- `kubectl` installed
- [Kagent](https://github.com/kubegpt-io/kagent) installed
- [OpenAI API Keys](https://platform.openai.com/)
- [Kyverno](https://platform.openai.com/) installed

---

### 2. Deploy Kagent

Follow quick-start instructions found here [[quickstart](https://kagent.dev/docs/getting-started/quickstart)] 

---

### 3. Add the Kyverno Agent and MCP Configuration

Apply the Kyverno agent custom resource:

```bash
kubectl apply -f kyverno-agent.yaml
kubectl apply -f kyverno-toolserver.yaml
kubectl apply -f kyverno-mcp.yaml
```

> The kagent UI configuration can be used instead of applying the yaml for simplicity

---

### 4. Example Prompts

- “Ensure all containers have memory and CPU limits.”
- “Auto-label namespaces with team=platform.”
- “Write a cleanup policy for Jobs older than 14 days.”
- “Only allow signed images from ghcr.io using cosign.”
- "Deploy a policy that mandates team label"
- "Show violations"
- "apply default policy sets for default namespace"

---

## Structure

- `kyverno-agent.yaml` – Kagent Agent definition with full instructions
- `kyverno-toolserver.yaml` - Tool definition file for Kagent
- `kyverno-mcp.yaml` - Kyverno MCP configuration
- `instructions` – Sample Agent Instructions
- `README.md` – This file
---