# 🏛️ Arquitetura Mobile

Escolher a arquitetura certa no mobile impacta diretamente na **escalabilidade**, **testabilidade** e **manutenibilidade** da aplicação.

---

## 🧱 MVC, MVP, MVVM

| Padrão | Características | Observações |
|--------|-----------------|-------------|
| MVC    | Model, View, Controller – lógica no Controller | Baixo isolamento de responsabilidades |
| MVP    | View interage com Presenter via interface | Testável, mas pode gerar boilerplate |
| MVVM   | ViewModel expõe dados com LiveData | Popular com Jetpack + Data Binding |

**MVVM** é o padrão mais utilizado hoje no Android com suporte oficial do Jetpack.

---

## 🧼 Clean Architecture

Separação em **camadas concêntricas**:

- **Domain**: regras de negócio.
- **Data**: repositórios, fontes externas.
- **Presentation**: ViewModels, UI.
- **DI**: injeção de dependência (Koin, Hilt).

Vantagens:
- Alta testabilidade.
- Baixo acoplamento.
- Independência da plataforma/framework.

---

## ♻️ Reutilização de Código

Boas práticas:
- Extraia código compartilhado em **módulos comuns** (`:core`, `:utils`, `:network`).
- Use bibliotecas multiplataforma como **KMM (Kotlin Multiplatform Mobile)** para Android + iOS.
- Centralize regras de negócio e modelos no domínio.

---

> Uma arquitetura bem definida melhora a qualidade, reduz bugs e acelera a evolução do app.