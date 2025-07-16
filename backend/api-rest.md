# 🌐 APIs REST

Este documento aborda conceitos essenciais e boas práticas para a construção e documentação de APIs REST modernas e escaláveis.

---

## 🔄 Padrão RESTful

REST (Representational State Transfer) é um estilo arquitetural para sistemas distribuídos baseado em recursos e operações HTTP padrão.

**Princípios principais:**

- **Recursos:** identificados por URIs (ex: `/usuarios`, `/produtos/123`).
- **Métodos HTTP:** operações CRUD via:
    - `GET` — recuperar recursos.
    - `POST` — criar recursos.
    - `PUT` — atualizar/repor recursos.
    - `PATCH` — atualização parcial.
    - `DELETE` — excluir recursos.
- **Stateless:** cada requisição deve conter todas as informações necessárias.
- **Representações:** recursos podem ser representados em JSON, XML, etc.
- **Camadas:** arquitetura deve ser composta por camadas independentes.

**Vantagens:**
- Simplicidade e padronização.
- Escalabilidade e independência entre cliente e servidor.
- Facilita cache e proxy intermediários.

---

## 🤝 HATEOAS (Hypermedia as the Engine of Application State)

HATEOAS é um princípio REST que sugere que as respostas da API devem incluir links para outras ações relacionadas, permitindo que clientes naveguem a API dinamicamente.

**Exemplo:**

```json
{
  "id": 123,
  "nome": "João",
  "links": [
    {"rel": "self", "href": "/usuarios/123"},
    {"rel": "pedidos", "href": "/usuarios/123/pedidos"}
  ]
}
```

**Benefícios:**

- **Desacopla cliente e servidor.**

- **Facilita evoluções na API sem quebrar clientes.**

- **Guia o cliente no uso correto dos recursos.**

---

### 📑 Swagger / OpenAPI

Swagger é um conjunto de ferramentas para especificar, construir, documentar e consumir APIs REST, baseado na especificação OpenAPI.

**Principais características:**

- **Define API com arquivo YAML ou JSON.**

- **Geração automática de documentação interativa (Swagger UI).**

- **Facilita testes manuais via interface web.**

- **Permite geração de clientes e servidores automaticamente.**

Exemplo básico de especificação OpenAPI:

```yaml
openapi: 3.0.1
info:
title: API de Usuários
version: "1.0"
paths:
/usuarios:
get:
summary: Lista todos usuários
responses:
'200':
description: Lista de usuários retornada com sucesso
```
---

## 🗂️ Versionamento de APIs

Versionar APIs é essencial para garantir compatibilidade e permitir evolução sem interrupção dos clientes existentes.

**Estratégias comuns:**

Na URL:
Exemplo: /api/v1/usuarios, /api/v2/usuarios

No cabeçalho HTTP:
Exemplo: Accept: application/vnd.myapi.v1+json

Query Parameters:
Exemplo: /usuarios?version=1

**Boas práticas:**

Mantenha versões antigas disponíveis enquanto clientes estiverem ativos.

Documente claramente mudanças entre versões.

Prefira versionamento na URL para maior simplicidade.

---

## ✅ Considerações Finais

Construir APIs RESTful robustas e bem documentadas, aderindo a padrões como HATEOAS, utilizando ferramentas como Swagger/OpenAPI e adotando estratégias claras de versionamento, é fundamental para garantir interoperabilidade, escalabilidade e boa experiência para os consumidores da API.

