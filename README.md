# 🧠 ai‑multi‑agency  
### Don’t settle for a single agent when you can have an entire agency.

---

## 🚀 Overview
**ai‑multi‑agency** is a platform‑agnostic system for defining and orchestrating AI agencies: structured teams of AI employees with roles, skills, workflows and independent model selection.

It provides a neutral specification that can be exported to multiple agent ecosystems such as OpenClaw, Hermes or Claude Workflows.

---

## 🏢 What is an AI Agency?
An AI agency is a structured organization composed of:

- **Employees** — AI workers with identity, role, skills and personality  
- **Roles** — backend dev, architect, PM, researcher…  
- **Skills** — codegen, analysis, testing, research…  
- **Workflows** — sequences of skill‑based steps  
- **Projects** — goals, deliverables and pipelines  
- **Architecture** — models, tools and runtime configuration  

Everything is defined in a **neutral YAML format**, independent of any specific platform.

---

## 🔌 Drivers
Drivers translate an agency into the native format of agent platforms:

- OpenClaw  
- OpenCode Hermes  
- Claude Workflows  
- Conversational Runtime (CLI)

LLM engines (Ollama, LM Studio, local servers, OpenAI, Claude API) do **not** require drivers.  
Each employee defines its own model and endpoint.

---

## 📦 Repository Structure

```
ai-multi-agency/
│
├── agencies/               # Example agencies
│   ├── dev-agency/
│   ├── marketing-agency/
│   └── content-agency/
│
├── spec/                   # Neutral agency specification
│   ├── agency.yaml
│   ├── employee.yaml
│   ├── skills.yaml
│   └── workflows.yaml
│
├── core/                   # Core logic
│   ├── parser/
│   ├── validator/
│   ├── generator/
│   └── registry/
│
├── drivers/                # Agent platform adapters
│   ├── openclaw/
│   ├── hermes/
│   ├── claude/
│   └── conversational/
│
├── cli/                    # CLI tool
│   └── ai-multi-agency.ts
│
├── docs/                   # Documentation
│   ├── branding/
│   ├── getting-started.md
│   ├── spec.md
│   └── roadmap.md
│
└── README.md
```

---

## 🛠️ Example Agency (YAML)

```yaml
agency:
  name: dev-agency
  description: "Software development AI agency."

  employees:
    - id: emp_001
      name: "Senior Developer"
      handle: "senior-dev"
      role: backend
      model:
        provider: local
        name: "qwen2.5-coder-14b"
        endpoint: "http://localhost:1234/v1"
      skills:
        codegen: 4
        refactor: 3
        testing: 2
      responsibilities:
        - "Implement features"
        - "Review code"
      persona:
        tone: "technical and direct"
        behavior: "step-by-step reasoning"

    - id: emp_002
      name: "Architect"
      handle: "architect"
      role: architecture
      model:
        provider: cloud
        name: "claude-3.7-sonnet"
      skills:
        analysis: 5
        design: 4
      responsibilities:
        - "Design architecture"
        - "Review technical decisions"

  workflows:
    - id: build_feature
      steps:
        - skill: analysis
        - skill: codegen
        - skill: testing

  projects:
    - id: ecommerce-platform
      goals:
        - "Implement payment module"
        - "Optimize performance"
```

---

## 🗺️ Roadmap

- [ ] Agency Spec v0.1
- [ ] Spec parser & validator
- [ ] CLI (ai-multi-agency)
- [ ] OpenClaw driver
- [ ] Hermes driver
- [ ] Claude Workflows driver
- [ ] Example agencies
- [ ] Full documentation
- [ ] v1.0 release

## 🧩 License
MIT License.

