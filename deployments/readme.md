# Deployment Parameters

This section defines the parameters for deploying your application in a Kubernetes environment.

- `minReadySeconds`: This parameter specifies the minimum number of seconds that Kubernetes should wait before considering the Pods healthy.
- `revisionHistoryLimit`: This parameter determines the number of old ReplicaSets that can be kept for potential rollbacks.
- Deployment Strategy: There are two available strategies:
  - **RollingUpdate**: This strategy updates the application gradually by replacing old Pods with new ones, ensuring minimal downtime.
  - **Recreate**: In this strategy, all existing Pods are terminated before deploying the new version. This approach may lead to downtime but can be useful for applications that can't coexist with multiple versions.

Before choosing the deployment strategy, consider whether your application can handle running different versions simultaneously. If coexistence could have adverse effects, the `Recreate` strategy might be suitable. However, note that `Recreate` deployments cannot achieve zero-downtime.

> **Note:** Always evaluate your application's requirements and constraints before selecting a deployment strategy.
