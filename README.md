# Observabilidade + ML

## Pré-requisitos

- Ferramenta kubectl instalada:

  https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

  https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/

- Já possuir um cluster Kubernetes criado ou criar um cluster local usando `Docker Desktop` e `k3d`

  https://docs.docker.com/desktop/

  https://k3d.io/

## Etapa Zero - Criação do cluster Kubernetes (distribuição K3S) usando k3d 

Após instalar o `kubectl`, `Docker Desktop` e o `K3D` siga os passos de acordo com seu SO.

### Linux
Cria o cluster Kubernetes
```bash
./bin/linux/task k3s-up
```
Verifica status do cluster Kubernetes
```bash
./bin/linux/task k3s-status
```
Se quiser remover o cluster Kubernetes
```bash
./bin/linux/task k3s-down
```

### Windows
Cria o cluster Kubernetes
```powershell
.\bin\windows\task.exe k3s-up
```
Verifica status do cluster Kubernetes
```powershell
.\bin\windows\task.exe k3s-status
```
Se quiser remover o cluster Kubernetes
```powershell
.\bin\windows\task.exe k3s-down
```

## Etapa 1 - Instalar ArgoCD

### Linux

Instalar  o ArgoCD

```bash
./bin/linux/task argocd-install
```

Acessar insterface gráfica do ArgoCD

```bash
./bin/linux/task argocd-access
```

### Windows

Instalar  o ArgoCD
```powershell
.\bin\windows\task.exe argocd-install
```

Acessar interface gráfica do ArgoCD

```powershell
.\bin\windows\task.exe argocd-access
```