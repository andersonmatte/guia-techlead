# 🔄 CI/CD

Integração Contínua (CI) e Entrega/Implantação Contínua (CD) são práticas essenciais para automatizar testes, builds e deploys de forma segura e eficiente.

---

## ⚙️ Jenkins

- Ferramenta tradicional de CI/CD com alta personalização.
- Baseado em pipelines definidos por scripts (Jenkinsfile).
- Grande variedade de plugins.

```groovy
pipeline {
  agent any
  stages {
    stage('Build') {
      steps { sh 'mvn clean package' }
    }
    stage('Test') {
      steps { sh 'mvn test' }
    }
  }
}
```

---

## 🚀 GitHub Actions

CI/CD embutido no GitHub.

Baseado em arquivos YAML no diretório .github/workflows/.

Fácil integração com repositórios e GitHub Packages.

```yaml
name: CI
on: [push]
jobs:
build:
runs-on: ubuntu-latest
steps:
- uses: actions/checkout@v4
- run: npm install && npm run build
```

---

## 🦊 GitLab CI

CI/CD nativo do GitLab.

Definido por .gitlab-ci.yml.

Suporte a múltiplos ambientes, artefatos e caches.

```yaml
stages:
- build
- deploy

build:
script:
- npm install
- npm run build

deploy:
script: ./deploy.sh
```

---

## 🛠️ Pipelines e Ambientes

Use ambientes separados: dev, staging, prod.

Versione os pipelines e configs de infraestrutura.

Faça deploy contínuo com gatilhos automáticos, rollback e aprovação manual.

CI/CD bem estruturado reduz erros humanos, acelera entregas e aumenta a confiabilidade.

