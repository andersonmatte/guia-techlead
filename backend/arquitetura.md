# 🏗️ Arquitetura Backend

Este documento apresenta os principais padrões e estilos arquiteturais utilizados no desenvolvimento de backends modernos, explicando conceitos, vantagens e quando aplicar.

---

## 🏛️ MVC (Model-View-Controller)

MVC é um padrão arquitetural clássico que separa a aplicação em três componentes principais:

- **Model**: representa os dados e regras de negócio.
- **View**: interface que apresenta dados para o usuário.
- **Controller**: camada intermediária que processa requisições e interage com Model e View.

**Vantagens:**
- Separação clara de responsabilidades.
- Facilita manutenção e testes.
- Muito usado em frameworks web tradicionais (Spring MVC, ASP.NET MVC).

**Quando usar:**
- Aplicações web com interface direta.
- Sistemas que precisam separar lógica de negócio da apresentação.

---

## 📦 DDD (Domain-Driven Design)

DDD é uma abordagem para desenvolver software focada no domínio de negócio e sua complexidade.

**Conceitos principais:**
- **Modelagem rica do domínio:** entidades, agregados, value objects.
- **Ubiquitous Language:** linguagem comum entre desenvolvedores e especialistas do negócio.
- **Bounded Contexts:** delimitação clara de subdomínios para evitar confusão.
- **Repositorios e Serviços de Domínio:** abstrações para manipular dados e regras.

**Vantagens:**
- Código alinhado ao negócio.
- Reduz complexidade ao dividir em contextos.
- Facilita evolução e manutenção do sistema.

**Quando usar:**
- Sistemas complexos, com regras de negócio robustas.
- Projetos de médio a grande porte.

---

## 🧩 Hexagonal Architecture (Ports and Adapters)

Arquitetura Hexagonal propõe isolar o núcleo da aplicação (domínio) das dependências externas através de portas (interfaces) e adaptadores.

**Componentes:**
- **Domínio central:** regras de negócio puras, independentes.
- **Ports:** interfaces que o domínio expõe ou consome.
- **Adapters:** implementações concretas das portas para bancos, UI, APIs, etc.

**Vantagens:**
- Independência da tecnologia externa.
- Testabilidade aprimorada.
- Facilita troca de tecnologias (banco, UI, serviços).

**Quando usar:**
- Sistemas que precisam ser altamente testáveis.
- Aplicações com várias formas de interação (API, UI, batch).

---

## ⚙️ Microservices

Arquitetura baseada em serviços pequenos, independentes e especializados, que se comunicam via APIs (geralmente REST ou mensageria).

**Características:**
- Cada serviço é implantado e escalado separadamente.
- Comunicação via protocolos leves.
- Cada serviço tem seu próprio banco de dados (idealmente).

**Vantagens:**
- Escalabilidade e resiliência.
- Times podem trabalhar de forma autônoma.
- Facilita manutenção e deploy contínuo.

**Desafios:**
- Complexidade operacional e de comunicação.
- Gestão de dados distribuídos.
- Monitoramento e segurança mais complexos.

**Quando usar:**
- Grandes sistemas com equipes independentes.
- Necessidade de escalar partes específicas do sistema.

---

## 🧹 Clean Architecture

Clean Architecture, proposta por Robert C. Martin (Uncle Bob), organiza o sistema em camadas concêntricas com dependências dirigidas para dentro, priorizando a independência do domínio.

**Camadas:**
- **Entities:** regras de negócio e entidades do domínio.
- **Use Cases:** lógica de aplicação que orquestra operações.
- **Interface Adapters:** adaptadores para UI, banco, APIs externas.
- **Frameworks & Drivers:** detalhes externos como banco, web frameworks.

**Princípios:**
- Dependências apontam para dentro.
- Domínio isolado de frameworks e UI.
- Facilita testes e manutenção.

**Quando usar:**
- Projetos que exigem alta qualidade e manutenibilidade.
- Sistemas que precisam de longevidade e fácil adaptação.

---

## ✅ Considerações Finais

Cada arquitetura tem seu contexto e indicações de uso. Muitas vezes, uma combinação de padrões é aplicada para atender às necessidades específicas do projeto. Entender os trade-offs é fundamental para escolher a melhor abordagem para seu backend.

