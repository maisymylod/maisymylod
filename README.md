# Maisy Mylod

Software engineer in New York with a pure mathematics background. I build LLM and
agent systems, infrastructure tooling, and applied ML. Most of what is below
runs: live demos, daily-retraining pipelines, and test suites you can execute
offline. The READMEs keep the claims matched to what the code actually does.

## Selected projects

**[gauntlet](https://github.com/maisymylod/gauntlet)** — Adversarial
test-and-defense harness for LLM agents. A 15-case attack corpus (direct and
indirect injection, jailbreak, exfiltration, tool abuse) run against a
configurable defense stack, with each defense's contribution measured separately
and an in-flight detector on top. The whole evaluation runs offline and
deterministically, no API key. Python.

**[outpost](https://github.com/maisymylod/outpost)** — Multi-target deployment
generator in Go. One workload spec renders to three environments: Terraform for
EKS, a Helm chart with a controller-runtime operator for on-prem Kubernetes, and
a self-contained air-gapped bare-metal bundle. Every artifact is validated by the
real tool (terraform, helm, kubeconform, shellcheck) in CI, and renders are
byte-for-byte deterministic. The multi-GPU wiring (NCCL, InfiniBand, device
plugins) is real in all three targets.

**[athena-ai](https://github.com/maisymylod/athena-ai)** — Deployed image
classifier separating AI-generated images from real photographs (EfficientNet-B0,
PyTorch). 0.996 accuracy and 0.9999 ROC-AUC on a held-out test set, with a model
card that states the single-dataset limits plainly.
[Live demo](https://mymaisy-athena-detect.hf.space/).

**[argus](https://github.com/maisymylod/argus)** — Natural-language earth
observation. An LLM agent calls geospatial tools (also exposed over the Model
Context Protocol), runs an NDVI and ONNX imagery pipeline on public Sentinel-2
data, and renders detections to a WebGL map. Runs offline with a deterministic
scripted agent; the same images run on Docker Compose and on a kind Kubernetes
cluster. Public data only.

**[nfl-moneyball](https://github.com/maisymylod/nfl-moneyball)** — Per-position
roster-value model that never imputes missing contract data to zero, flags every
contract match's quality, and routes low-sample players to an audit file.
Retrains daily via GitHub Actions and publishes to a
[live dashboard](https://maisymylod.github.io/nfl-moneyball/).

**[truth-editor](https://github.com/maisymylod/truth-editor)** — Fact-check layer
for LLM output. Extracts atomic claims and verifies each against the live web in
parallel, returning a verdict and sources per claim.

## Background

B.S. Pure Mathematics, University of Michigan. Currently a software engineer
building production Rails and Postgres systems. Previously in data analytics at
CLEAR.

[Website](https://maisymylod.github.io/maisy-mylod-website/) · [LinkedIn](https://linkedin.com/in/maisymylod)
