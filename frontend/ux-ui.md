# 🎨 UX/UI

Experiência e interface do usuário são partes críticas do sucesso de um frontend.

---

## 📱 Design Responsivo

Use `media queries`, `flexbox` e `grid` para adaptar a tela a diferentes tamanhos.

Exemplo com Flexbox:
```css
.container {
  display: flex;
  flex-direction: column;
}
```
Use rem, em, % em vez de px fixos.

---

## 🎨 Material Design

- **Padrão visual desenvolvido pelo Google.**

- **Componentes Angular com @angular/material**

- **Consistência, responsividade e acessibilidade embutidas**

*Instale:*

```bash
ng add @angular/material
```

---

## ♿ Acessibilidade (a11y)

- **Inclua todos os usuários. Boas práticas:**

- **Use aria-label, role, e alt.**

- **Certifique-se de que tudo é acessível via teclado.**

- **Mantenha contraste e tamanho de fonte adequados.**

- **Ferramentas: axe, Lighthouse, eslint-plugin-a11y**

---

## 📱 Mobile First

- **Projete primeiro para telas pequenas e expanda para maiores.**

- **Menos elementos, foco no essencial**

- **Layout adaptativo com min-width, não max-width**

- **UX bem pensado reduz atrito, aumenta retenção e gera valor real ao usuário.**
