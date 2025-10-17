# 🧭 Platform Engineering Observability Demo

**Building a Developer-Centric Open Observability Platform on Kubernetes with OpenTelemetry, Perses, and Dash0**

![alt text](observability-article-perses.png)

---

## 🚀 Overview

Modern platform teams have moved beyond adding “just another dashboard.”
**Observability today is a platform capability — not a tool.**

When developers can self-serve metrics, traces, and logs directly from their services, they stop filing tickets and start learning from production in real time.
When platform engineers ship that capability as a reusable internal product, **developer experience and operational feedback loops converge.**

This repository demonstrates a **Kubernetes-native observability stack** powered by **OpenTelemetry**, **Perses**, and **Dash0**, designed as both an **operational system** and a **product experience**.

> “When observability is designed as a product, developers don’t just see systems — they understand them.”

---

## 🎯 Objectives

This demo shows how to:

* Design and deploy a **complete, developer-centric observability platform** on Kubernetes.
* Use **OpenTelemetry** to standardize telemetry across polyglot services.
* Leverage **Perses** for **dashboards-as-code** and repeatable visibility.
* Integrate **Dash0** as the activation layer, transforming telemetry into correlated, actionable datasets.
* Bridge **platform engineering** and **product management** mindsets to define observability success.

---

## 🧩 Why This Stack

| Platform Goal             | Product Outcome                               |
| ------------------------- | --------------------------------------------- |
| Automated instrumentation | Developer self-service observability          |
| Multi-layer collectors    | Contextual performance insights               |
| Unified telemetry flow    | Measurable DevEx improvements                 |
| Dashboards-as-code        | Repeatable learning patterns                  |
| Dash0 integration         | Strategic visibility through data correlation |

This project demonstrates how **open telemetry standards**, **automated instrumentation**, and **dashboards-as-code** form the backbone of **Observability-as-a-Service** inside modern internal platforms.

---

## 🧱 Stack Components

* **OpenTelemetry** – Telemetry standardization and auto-instrumentation.
* **Perses** – Open, declarative dashboarding for reproducible visibility.
* **Dash0** – Data activation and correlation across signals.
* **Prometheus / Jaeger / OpenSearch** – Metrics, traces, and logs backends.
* **Kind + Helm** – Local Kubernetes orchestration and reproducible automation.

---

## 🗂️ Repository Structure

```
platform-observability-demo/
├── collector/                # OpenTelemetry collector configs
├── instrumentations/         # Auto-instrumentation CRDs
├── jaeger/                   # Jaeger values
├── kind/                     # Cluster config (multi-node)
├── opensearch/               # Log storage and dashboard config
├── perses/                   # Dashboards-as-code
├── prometheus/               # Metrics storage
├── services/                 # Demo microservices (Go, Java, Frontend)
├── Makefile                  # Reproducible automation
├── .env.template             # Environment configuration template
└── README.md                 # You are here
```

---

## 🧰 Prerequisites

* **Docker** – Build and load local images
* **Kind** – Local Kubernetes cluster
* **kubectl** – Cluster resource management
* **Helm** – Chart deployment
* **Kustomize** – Manifest management
* **Dash0 Account + Auth Token** – OTLP export layer

Optional:

* `jq`, Internet access, and ≥8 GB RAM recommended.

---

## ⚙️ Quick Start

### Option A: One-Line Full Deployment

```bash
export DASH0_AUTH_TOKEN="your-dash0-token"
make deploy-all
```

This command provisions a multi-node Kind cluster and deploys the full observability stack — OpenTelemetry, Prometheus, Jaeger, OpenSearch, Perses, Dash0 integration, and demo microservices — in ≈10 minutes.

### Option B: Step-by-Step Walkthrough

See the article for a detailed, phase-by-phase guide:
[**Building a Developer-Centric Open Observability Stack on Kubernetes**](#)

---

## 🔍 Validation

Once deployed, access each service locally:

| Service               | Command                                                    | URL                                              |
| --------------------- | ---------------------------------------------------------- | ------------------------------------------------ |
| Frontend              | `kubectl port-forward svc/frontend 3000:80`                | [http://localhost:3000](http://localhost:3000)   |
| Prometheus            | `kubectl port-forward svc/prometheus 9090:9090`            | [http://localhost:9090](http://localhost:9090)   |
| Jaeger                | `kubectl port-forward svc/jaeger-query 16686:16686`        | [http://localhost:16686](http://localhost:16686) |
| OpenSearch Dashboards | `kubectl port-forward svc/opensearch-dashboards 5601:5601` | [http://localhost:5601](http://localhost:5601)   |
| Perses                | `kubectl port-forward svc/perses 8080:8080`                | [http://localhost:8080](http://localhost:8080)   |

---

## 🧭 Learning Outcomes

* Understand how observability evolves from tooling to **platform capability**.
* Learn how to **automate instrumentation** and **standardize telemetry** using OpenTelemetry.
* Implement **dashboards-as-code** for consistency and collaboration.
* Explore **Dash0** for signal correlation and developer-centric insights.
* Bridge **technical delivery** with **product learning loops**.

---

## 💡 Key Takeaways

* **Observability by Default** – Instrumentation should ship with the platform, not as an afterthought.
* **Data as Feedback** – Treat telemetry as learning loops, not just logs.
* **Dashboards as Narrative** – Use dashboards to connect developer intent to production behavior.
* **Platform as Product** – Deliver observability as a self-service internal capability.

---

## 🧼 Cleanup

```bash
make delete-cluster
```

Removes all resources and resets your environment.

---

## 🧠 Author

**Victor Ikeme**
*Technical Platform Product Manager · Cloud Platforms Architect*
Host of **Build Platforms Daily**
📘 [victor-ikeme/platform-observability-demo](https://github.com/victor-ikeme/platform-observability-demo)

---

## 🏷️ SEO Tags

`#platformengineering` `#observability` `#opentelemetry` `#perses` `#dash0`
`#kubernetes` `#devex` `#internaldeveloperplatform` `#cloudnative`
`#dashboardsascode` `#platformproductmanagement` `#SRE` `#developerexperience`

