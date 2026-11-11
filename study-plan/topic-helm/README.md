# Helm Study Plan

**Helm** is the package manager for Kubernetes. It lets you define, install, upgrade, and manage Kubernetes applications using reusable, versioned packages called *charts*.

---

## Prerequisites

### Tools to Install
- **kubectl** — Kubernetes CLI: https://kubernetes.io/docs/tasks/tools/
- **Helm** — https://helm.sh/docs/intro/install/
- **A Kubernetes cluster** — Options:
  - Local: [Minikube](https://minikube.sigs.k8s.io/), [kind](https://kind.sigs.k8s.io/), [Docker Desktop with Kubernetes](https://docs.docker.com/desktop/kubernetes/)
  - Cloud: AKS, EKS, GKE (any will work)
- **Jupyter** — to run the notebooks: `pip install jupyterlab`

### Prior Knowledge Assumed
- Basic Kubernetes concepts (Pods, Deployments, Services, Namespaces)
- Familiarity with YAML syntax
- Basic command-line usage

---

## Recommended Resources

| Resource | URL |
|---|---|
| Helm Official Docs | https://helm.sh/docs |
| Helm GitHub | https://github.com/helm/helm |
| Artifact Hub (chart search) | https://artifacthub.io |
| Helm Chart Best Practices | https://helm.sh/docs/chart_best_practices/ |
| Chart Template Guide | https://helm.sh/docs/chart_template_guide/ |
| Sprig Template Functions | https://masterminds.github.io/sprig/ |
| Helm Cheat Sheet (community) | https://helm.sh/docs/intro/cheatsheet/ |

---

## Study Plan Overview

| Phase | Topic | Lessons | Est. Time |
|---|---|---|---|
| 1 | Foundations | 4 lessons | ~2 hours |
| 2 | Chart Anatomy & Templates | 4 lessons | ~3 hours |
| 3 | Advanced Templates | 4 lessons | ~3 hours |
| 4 | Dependencies & Hooks | 3 lessons | ~2.5 hours |
| 5 | Real-World Workflows | 4 lessons | ~3 hours |
| Capstone | Multi-Service App Deployment | 1 project | ~4 hours |

**Total: 19 lessons + 1 capstone ≈ 17–18 hours**

---

## Lessons

### Phase 1 — Foundations

| Lesson | Title | Notebook |
|---|---|---|
| 1.1 | What Is Helm? | [lesson-1.1-what-is-helm.ipynb](phase-1-foundations/lesson-1.1-what-is-helm.ipynb) |
| 1.2 | Installation & Environment Setup | [lesson-1.2-installation-setup.ipynb](phase-1-foundations/lesson-1.2-installation-setup.ipynb) |
| 1.3 | Your First Chart Install | [lesson-1.3-first-chart-install.ipynb](phase-1-foundations/lesson-1.3-first-chart-install.ipynb) |
| 1.4 | Helm CLI Basics | [lesson-1.4-helm-cli-basics.ipynb](phase-1-foundations/lesson-1.4-helm-cli-basics.ipynb) |

### Phase 2 — Chart Anatomy & Templates

| Lesson | Title | Notebook |
|---|---|---|
| 2.1 | Chart File Structure | [lesson-2.1-chart-structure.ipynb](phase-2-chart-anatomy/lesson-2.1-chart-structure.ipynb) |
| 2.2 | Chart.yaml & values.yaml | [lesson-2.2-chart-yaml-and-values.ipynb](phase-2-chart-anatomy/lesson-2.2-chart-yaml-and-values.ipynb) |
| 2.3 | Writing Your First Template | [lesson-2.3-writing-templates.ipynb](phase-2-chart-anatomy/lesson-2.3-writing-templates.ipynb) |
| 2.4 | Built-in Objects & Rendering | [lesson-2.4-builtin-objects.ipynb](phase-2-chart-anatomy/lesson-2.4-builtin-objects.ipynb) |

### Phase 3 — Advanced Templates

| Lesson | Title | Notebook |
|---|---|---|
| 3.1 | Template Functions & Pipelines | [lesson-3.1-functions-pipelines.ipynb](phase-3-advanced-templates/lesson-3.1-functions-pipelines.ipynb) |
| 3.2 | Control Flow: if, with, range | [lesson-3.2-control-flow.ipynb](phase-3-advanced-templates/lesson-3.2-control-flow.ipynb) |
| 3.3 | Named Templates & Helpers | [lesson-3.3-helpers-and-partials.ipynb](phase-3-advanced-templates/lesson-3.3-helpers-and-partials.ipynb) |
| 3.4 | Values Schema Validation | [lesson-3.4-values-schema.ipynb](phase-3-advanced-templates/lesson-3.4-values-schema.ipynb) |

### Phase 4 — Dependencies & Hooks

| Lesson | Title | Notebook |
|---|---|---|
| 4.1 | Chart Dependencies | [lesson-4.1-chart-dependencies.ipynb](phase-4-dependencies-hooks/lesson-4.1-chart-dependencies.ipynb) |
| 4.2 | Subcharts & Global Values | [lesson-4.2-subcharts-global-values.ipynb](phase-4-dependencies-hooks/lesson-4.2-subcharts-global-values.ipynb) |
| 4.3 | Hooks & Release Lifecycle | [lesson-4.3-hooks.ipynb](phase-4-dependencies-hooks/lesson-4.3-hooks.ipynb) |

### Phase 5 — Real-World Workflows

| Lesson | Title | Notebook |
|---|---|---|
| 5.1 | OCI Registries & Chart Publishing | [lesson-5.1-oci-registries.ipynb](phase-5-real-world/lesson-5.1-oci-registries.ipynb) |
| 5.2 | Helm Test | [lesson-5.2-helm-test.ipynb](phase-5-real-world/lesson-5.2-helm-test.ipynb) |
| 5.3 | Best Practices & Linting | [lesson-5.3-best-practices.ipynb](phase-5-real-world/lesson-5.3-best-practices.ipynb) |
| 5.4 | CI/CD Integration | [lesson-5.4-cicd.ipynb](phase-5-real-world/lesson-5.4-cicd.ipynb) |

### Capstone Project

| Title | Notebook |
|---|---|
| Deploy a Multi-Service App with a Custom Chart | [capstone-project.ipynb](capstone/capstone-project.ipynb) |

---

## Capstone Overview

**Scenario:** You are a platform engineer at a company deploying a two-service application (a backend API + a frontend web server) to Kubernetes. You will:

1. Author a production-grade Helm chart for both services from scratch
2. Configure separate `values-dev.yaml`, `values-staging.yaml`, and `values-prod.yaml` overrides
3. Add a `pre-install` hook that runs a database schema migration Job
4. Define chart dependencies (e.g., a PostgreSQL subchart)
5. Lint and test the chart with `helm lint` and `helm test`
6. Package the chart and push it to an OCI registry
7. Simulate a CI pipeline with `helm template | kubectl apply --dry-run`

---

## How to Use These Notebooks

1. Install Jupyter: `pip install jupyterlab`
2. Launch: `jupyter lab` from the `study-plan/topic-helm/` directory
3. Open the first notebook: `phase-1-foundations/lesson-1.1-what-is-helm.ipynb`
4. Run cells **top-to-bottom** — each cell builds on the previous
5. Complete `# TODO:` / `# TASK:` exercises before moving on
6. Each notebook ends with a link to the next lesson

> **Note:** Cells that run `helm`, `kubectl`, or bash commands require a working Kubernetes cluster and Helm installation. Use `%%bash` cells or `!command` syntax in notebooks.
