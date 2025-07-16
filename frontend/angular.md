# 🅰️ Angular

Angular é um framework robusto para construção de aplicações frontend em larga escala, desenvolvido e mantido pelo Google.

---

## ⚙️ Angular CLI

Ferramenta de linha de comando para scaffolding, build, testes e otimizações.

```bash
ng new projeto
ng generate component usuario
ng serve
```

*Vantagens:*

- **Geração de código padronizado.**

- **Automação de testes e builds.**

- **Integração com lint, SSR e i18n.**

---

## 🧩 Componentes e Módulos

Componentes: unidades visuais e funcionais da interface.

Módulos: agrupadores lógicos de funcionalidades.

*Boas práticas:*

- **Modularize por feature (UsuarioModule, AdminModule).**

- **Use SharedModule para componentes reutilizáveis.**

---

## 🛰️ Services e HttpClient

Use serviços para lógica de negócio e comunicação HTTP com APIs REST.

```ts
constructor(private http: HttpClient) {}
getUsuarios() {
return this.http.get('/api/usuarios');
}
```

*Boas práticas:*

- **Centralize chamadas em serviços.**

- **Tipifique as respostas com interfaces.**

---

## 🧾 Forms e RxJS

Reactive Forms: mais controle e validação dinâmica.

RxJS: programação reativa com Observables.

```ts
form = new FormGroup({
nome: new FormControl('', Validators.required)
});

form.valueChanges.subscribe(valor => console.log(valor));
```
--- 

## 🧭 Routing

Gerencia navegação e URLs no Angular:

```ts
const routes: Routes = [
{ path: 'login', component: LoginComponent },
{ path: 'dashboard', component: DashboardComponent }
];
```

Inclua guards, resolvers e lazy loading para rotas protegidas e performáticas.

---

## 🧱 Standalone Components
Desde Angular 14, componentes podem ser standalone, sem necessidade de módulos.

```ts
@Component({
standalone: true,
imports: [CommonModule],
template: `<h1>Hello</h1>`
})
export class HelloComponent {}

```
*Vantagens:*

- **Mais leves.**

- **Melhor reutilização e testes.**

---

## 🌐 Angular Universal

Renderização do Angular no servidor (SSR).

*Vantagens:*

- **Melhor SEO.**

- **Melhor desempenho na primeira carga.**

Use:

```bash
ng add @nguniversal/express-engine
```
Angular é ideal para grandes projetos, com forte estrutura, tipagem e ferramentas oficiais.
