# 🧪 Testes Frontend

Testes são fundamentais para evitar regressões e garantir qualidade no desenvolvimento frontend.

---

## 🔍 Jasmine e Karma

Padrão em projetos Angular.

- Jasmine: framework de testes.
- Karma: test runner no navegador.

```ts
describe('Componente', () => {
  it('deve retornar verdadeiro', () => {
    expect(true).toBeTrue();
  });
});
```

Use TestBed para isolar dependências.

---

## 🧪 Testes de Componentes

Utilize ComponentFixture para manipular o DOM e interagir com elementos:

```ts
fixture.detectChanges();
expect(fixture.nativeElement.querySelector('h1').textContent).toContain('Olá');
```
*Inclua testes para:*

- **Inputs e outputs**

- **Formulários**

- **Interação com serviços mockados**

---

## 🧭 Testes E2E com Cypress

Substitui o Protractor e simula o uso real do app.

```ts
cy.visit('/login');
cy.get('input[name=email]').type('teste@email.com');
cy.contains('Entrar').click();
```
*Boas práticas:*

- **Use data-testid para seletores.**

- **Evite flutuações: cy.intercept() para mockar APIs.**

- **Automatize os testes no pipeline e escreva testes que reflitam o comportamento real do usuário.**