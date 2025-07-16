# 🧹 Boas Práticas Frontend

Dicas essenciais para escrever um frontend limpo, performático e sustentável.

---

## 🗂️ Estrutura de Pastas

Prefira **estrutura por funcionalidades**, e não por tipo:

/usuario
usuario.component.ts
usuario.service.ts
usuario.module.ts

```yaml

Utilize `/shared`, `/core`, `/features` para organizar componentes reutilizáveis, serviços globais e módulos.
```

---

## ♻️ DRY & KISS

- **DRY (Don't Repeat Yourself)**: evite duplicação.
- **KISS (Keep It Simple, Stupid)**: soluções simples são mais fáceis de manter.

💡 Extraia lógicas comuns para **pipes, directives, e serviços reutilizáveis.**

---

## 📡 Observables e `async` pipe

Use `async` pipe no HTML ao invés de `.subscribe()` no componente.

```html
<div *ngIf="dados$ | async as dados">
  {{ dados.nome }}
</div>
```

*Vantagens:*

- **Gerenciamento automático de subscrição.**

- **Redução de código no TypeScript.**

---

## ⚡ Performance e Lazy Loading

- **Divida rotas e módulos com lazy loading (loadChildren).**

- **Implemente trackBy em ngFor.**

- **Use ChangeDetectionStrategy.OnPush para componentes de alta performance.**

- **Carregue imagens responsivas e com lazy loading nativo (loading="lazy").**

- **Código limpo, bem organizado e performático é um diferencial competitivo no frontend.**