# togglemaster-gitops

Fonte de verdade dos manifestos Kubernetes do ToggleMaster (Tech Challenge Fase 3).
Nada aqui contém segredo: as credenciais vêm do AWS Secrets Manager via External Secrets Operator.

- apps/<serviço>/: deployment, service, configmap, ExternalSecret (e HPA/ServiceAccount quando existem)
- base/: namespaces, ClusterSecretStore e Ingress
- argocd/: uma Application por componente; o ArgoCD lê esta pasta (app-of-apps) e sincroniza sozinho

A tag da imagem em apps/<serviço>/deployment.yaml é alterada pelo pipeline de CI de cada serviço.
