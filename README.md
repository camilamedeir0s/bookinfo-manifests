# 📦 Bookinfo Manifests with Service Weaver

This repository contains Kubernetes manifests for deploying the Bookinfo application adapted to use the [Service Weaver](https://serviceweaver.dev/) framework. The main version includes distributed tracing support with Jaeger.

## 📁 Repository Structure

- **`tracing-100products/`**: This is the main deployment configuration. It contains the manifests for the Bookinfo application with tracing enabled. This version is designed for use in performance and observability experiments, and is fully instrumented to collect distributed traces across service boundaries.
  
- **`no-tracing-100products/`**: This is a legacy version of the application without tracing instrumentation. It is preserved for reference purposes or fallback use, and is not expected to evolve further.

## 📌 Deployment Instructions

To deploy the application, select **one configuration file at a time** from the desired directory and apply it using `kubectl`.

For example, to deploy the version with tracing and colocated services, use the file named `a-colocated.yaml` located in the `tracing-100products/` directory.

Only **one YAML file should be applied per deployment**, as each file represents a complete configuration with specific service grouping and layout.

```bash
kubectl apply -f tracing-100products/<configuration>.yaml
