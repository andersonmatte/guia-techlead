# ☁️ Cloud

A computação em nuvem oferece flexibilidade, escalabilidade e alta disponibilidade com modelos sob demanda.

---

## 🌩️ AWS

- **EC2**: instâncias de máquinas virtuais escaláveis.
- **S3**: armazenamento de objetos, altamente durável.
- **RDS**: banco de dados relacional gerenciado (MySQL, PostgreSQL, etc).

Boas práticas:
- Use IAM para controlar permissões.
- Habilite backup e versionamento.
- Distribua carga com ELB + Auto Scaling.

---

## ☁️ GCP e Azure

- GCP: Compute Engine, Cloud Storage, Cloud SQL, GKE.
- Azure: Virtual Machines, Blob Storage, Azure SQL, AKS.

Ambas oferecem:
- Deploy serverless (Cloud Functions / Azure Functions)
- Monitoramento nativo
- Infraestrutura como código

---

## 📐 Boas Práticas de Arquitetura

- Isolar ambientes (VPCs, Subnets).
- Implementar observabilidade (logs, métricas, alertas).
- Automatizar via **Terraform / CloudFormation**.
- Minimizar acoplamento com serviços proprietários.

---

> Entender cloud vai além do provisionamento: envolve governança, segurança, automação e boas práticas de design.
