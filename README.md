# Plataforma de Observabilidade com Machine Learning

Este projeto fornece uma **plataforma de observabilidade** com Kubernetes e Machine Learning, usando [SigNoz](https://signoz.io/) como ferramenta central. Toda a automação é feita via `Task` e o controle de implantação usa o ArgoCD.

A plataforma é pensada para rodar em **clusters Kubernetes reais**, mas **pode ser executada localmente** para testes com `Docker Desktop`, `K3D` e um cluster local `K3S`.

---

## ✅ Pré-requisitos

- [`kubectl`](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/) instalado
- [`Docker Desktop`](https://docs.docker.com/desktop/) instalado
- [`K3D`](https://k3d.io/) instalado

---

## ⚙️ Automação com `Task`

Esta plataforma utiliza a ferramenta [`Task`](https://taskfile.dev) para automatizar tarefas comuns.

### Como usar:

#### Windows
```powershell
.\bin\windows\task.exe
```

#### Linux
```bash
./bin/linux/task
```

Para listar as tarefas disponíveis:
```bash
task --list
```

---

## 🚀 Tarefas Disponíveis

```
task: Available tasks for this project:
* argocd-access:            Port-Forward para acessar a interface gráfica do ArgoCD
* argocd-apps-create:       Cria ArgoCD Apps e inicia instalação de aplicações no cluster
* argocd-install:           Instala o ArgoCD no cluster k3s
* cluster-down:             Deleta o cluster k3s
* cluster-list:             Lista o cluster criado
* cluster-status:           Mostra os nós do cluster criado
* cluster-up:               Cria o cluster k3s
```

---

## 🔧 Etapa 0 – Criar o cluster Kubernetes com K3D (opcional para testes locais)

Se você **não possui um cluster Kubernetes** já configurado, pode rodar tudo localmente com:

### Linux
```bash
./bin/linux/task cluster-up
./bin/linux/task cluster-status
./bin/linux/task cluster-down
```

### Windows
```powershell
.\bin\windows\task.exe cluster-up
.\bin\windows\task.exe cluster-status
.\bin\windows\task.exe cluster-down
```

---

## 🧩 Etapa 1 – Instalar o ArgoCD

### Linux
```bash
./bin/linux/task argocd-install
./bin/linux/task argocd-access
```

### Windows
```powershell
.\bin\windows\task.exe argocd-install
.\bin\windows\task.exe argocd-access
```

---

## 📈 Plataforma de Observabilidade com SigNoz

Após a instalação do ArgoCD, a **plataforma de observabilidade** será implantada usando [SigNoz](https://signoz.io/), uma alternativa completa ao Grafana + Prometheus. O SigNoz já inclui coleta de métricas, logs e traces.

A instalação do SigNoz será gerenciada por meio dos manifests definidos nos apps do ArgoCD.

---

