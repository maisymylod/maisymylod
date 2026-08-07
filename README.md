# Maisy Mylod

*AI and agent-systems engineer with a security focus and a pure-mathematics foundation. I build and ship LLM-based agentic systems end to end.*

I design multi-agent LLM systems, the data and security layers underneath them, and the infrastructure that deploys them, including to air-gapped environments. I treat security as a design property rather than a bolt-on, and I keep every claim matched to what the code does: the repositories below run, are tested, and report real numbers from actually running.

## Flagship: the Heliosnet ground system

Four interoperating projects that simulate a satellite constellation's ground segment: the data plane, the brains, the shield, and the deploy system. One coherent system. `liftoff` deploys the stack that `groundstation` operates over `constellation`'s telemetry, with `aegis` authenticating the command path. Each project also stands alone and runs on its own.

| Project | What it is | Real headline number |
|---|---|---|
| [constellation](https://github.com/maisymylod/constellation) | Telemetry data plane: streaming ingestion (Redpanda → TimescaleDB), unsupervised anomaly detection, and a React/TypeScript ops console | Anomaly detection F1 **0.720** (recall 0.808) on held-out satellites, over 180,000 streamed telemetry records |
| [groundstation](https://github.com/maisymylod/groundstation) | Agentic mission-ops copilot: a LangGraph multi-agent graph operating the system through MCP tools and RAG-cited playbooks, with tiered model routing and a human-in-the-loop approval gate | Trained anomaly-type classifier **96.7%** accuracy, **0.931** macro-F1 (held-out satellites) |
| [aegis](https://github.com/maisymylod/aegis) | Security layer: Ed25519 signed-command authentication (replay protection, key rotation, verifying chain), mutual TLS, and an adversarial harness with a measured defense stack | 19-case corpus, **19/19** succeed undefended and **0/19** defended. Eight cases were written by reading each guard and going around it: **seven worked**, dropping the block rate to **63%** before the gaps were closed |
| [liftoff](https://github.com/maisymylod/liftoff) | Deploy and build-reliability layer (Go): one declarative suite spec rendered for cloud, on-prem, and air-gapped bare-metal, with SLO-driven rollback | All **three** targets pass terraform, helm/kubeconform, and shellcheck, with byte-for-byte deterministic output |

## Other work

- [athena-ai](https://github.com/maisymylod/athena-ai): a deployed real-vs-AI image classifier (EfficientNet-B0) served behind an API with a live demo: **0.996** accuracy and **0.9999** ROC-AUC on held-out data, a verdict in roughly **150 ms**, and an honest model card.
- [slew](https://github.com/maisymylod/slew): a 3-DOF spacecraft attitude-control simulator in C++20: quaternion-feedback control over real rigid-body dynamics (Euler's equations) with a saturating actuator. A default 30-degree slew settles to **0.0008-degree** final error at a 1 kHz control rate, with a bit-identical trajectory every run. An optional four-wheel reaction-wheel model exchanges momentum instead of inventing torque, conserving inertial angular momentum to **8.4e-6** of the momentum exchanged.

## Tech

- **Languages**: Python, Go, C++, TypeScript/JavaScript, SQL
- **AI / agents**: LangGraph multi-agent orchestration, MCP (servers and clients), RAG over a vector DB (pgvector), tiered Anthropic Claude model routing, PyTorch model training and evaluation
- **Data**: Kafka / Redpanda, stream processing, TimescaleDB and time-series, anomaly detection, pandas / NumPy / scikit-learn
- **Security**: prompt-injection / jailbreak / exfiltration red-teaming, Ed25519 signed command authentication, mutual TLS, replay protection, threat modeling
- **Infrastructure**: Terraform (EKS + GPU node groups), Helm, Kubernetes CRDs and controller-runtime operators, Docker, GitHub Actions, air-gapped and GPU deployment

## Portfolio

[maisymylod.github.io/maisy-mylod-website](https://maisymylod.github.io/maisy-mylod-website/)
