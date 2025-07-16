# 🐳 Docker & Kubernetes

Contêineres e orquestradores modernos são a base da infraestrutura moderna de microsserviços.

---

## 🧱 Containers

- Isolamento leve, rápido e portátil.
- Ideal para criar ambientes consistentes entre dev, staging e produção.

---

## 🐳 Dockerfiles

Definem como a imagem do container será construída.

```dockerfile
FROM node:18
WORKDIR /app
COPY . .
RUN npm install
CMD ["npm", "start"]
```

*Boas práticas:*

Imagens leves (use Alpine)

Minimizar camadas

Ignorar arquivos desnecessários com .dockerignore

---

## ☸️ Kubernetes Basics

Pod: menor unidade de execução (roda containers).

Deployment: define número de réplicas e atualizações.

Service: expõe o app dentro ou fora do cluster.

Ingress: gerencia rotas HTTP/HTTPS externas.

*Comandos úteis:*

```bash
kubectl get pods
kubectl apply -f deployment.yaml
kubectl logs <pod>
```
---

## ⚙️ Helm Charts

Ferramenta de empacotamento e versionamento de configurações Kubernetes.

Facilita deploy padronizado de aplicações complexas.

```bash
helm install meu-app ./chart
```
Docker e Kubernetes permitem escalar, versionar e entregar aplicações com alta consistência e automação.

