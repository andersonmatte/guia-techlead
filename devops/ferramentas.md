# 🛠️ Ferramentas DevOps

Ferramentas que suportam automação de infraestrutura, provisionamento, segurança e entrega contínua.

---

## ⚙️ Terraform

- Infraestrutura como Código (IaC).
- Compatível com AWS, GCP, Azure, Kubernetes etc.
- Usa linguagem declarativa (`.tf`).

```hcl
resource "aws_s3_bucket" "meu_bucket" {
  bucket = "minha-app-bucket"
  acl    = "private"
}
```

---

## 🤖 Ansible

Automação de provisionamento e configuração.

Baseado em YAML (playbooks).

Agente-less (não precisa instalar em cada host).

```yaml
- hosts: servidores
  tasks:
    - name: Instalar Nginx
      apt:
        name: nginx
        state: present
```

---

## 🔄 ArgoCD

Deploy GitOps para Kubernetes.

Monitora repositórios Git e aplica mudanças automaticamente.

Interface web para visualizar o estado dos apps.

---

## 🔐 Vault

Gerenciador seguro de segredos, tokens e credenciais.

Criptografia de dados em repouso e em trânsito.

Pode integrar com Kubernetes, AWS, banco de dados e mais.

Essas ferramentas compõem o ecossistema de entrega moderna, segura e automatizada.