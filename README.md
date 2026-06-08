# Home Assistant Helm Chart

Baseline Helm chart for [Home Assistant](https://www.home-assistant.io/) on Kubernetes. Uses the maintained [pajikos/home-assistant-helm-chart](https://github.com/pajikos/home-assistant-helm-chart).

## Subcharts

| Subchart | Source | Values prefix | Description |
|----------|--------|---------------|-------------|
| **home-assistant** | [pajikos chart](https://github.com/pajikos/home-assistant-helm-chart) | `home-assistant.*` | Deployment, ingress, persistence, probes. |

## Configuration

Override in your values: ingress hosts, `persistence.existingClaim` or PVC size, `env` (TZ), and `controller.type` (`Deployment` when using `existingClaim`).

Defaults use `home-assistant.example.com`, a 5Gi PVC, and `TZ: UTC`.

## Install

```bash
helm dependency update .
helm template release . -f values.yaml
```
