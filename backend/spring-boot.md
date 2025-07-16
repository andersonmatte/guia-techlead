# 🚀 Spring Boot — Guia Completo

O Spring Boot é o principal framework para desenvolvimento de aplicações Java modernas e produtivas. Ele simplifica a configuração, estrutura e execução de aplicações Java corporativas.

---

## 🏁 Introdução ao Spring Boot

- Construído sobre o Spring Framework.
- Fornece uma estrutura opinativa e pronta para produção.
- Minimiza configuração XML.
- Vem com servidor embutido (Tomcat, Jetty ou Undertow).

---

## ⚙️ Inicialização do Projeto

### Usando Spring Initializr

Acesse [start.spring.io](https://start.spring.io) e configure:

- Projeto: Maven ou Gradle
- Linguagem: Java
- Versão: 17 ou superior
- Dependências comuns: Spring Web, Spring Data JPA, Spring Security, Validation, Lombok, Spring Boot DevTools

### Estrutura típica

```
src/
├── main/
│   ├── java/
│   │   └── com/exemplo/app/
│   │       ├── AppApplication.java
│   │       ├── controller/
│   │       ├── service/
│   │       ├── repository/
│   │       └── model/
│   └── resources/
│       ├── application.properties
│       └── static/
└── test/
```

---

## 🔧 Módulos Principais

### 🌐 Spring Web

- Criação de APIs REST usando `@RestController`
- Mapeamento com `@GetMapping`, `@PostMapping`, etc.

```java
@RestController
@RequestMapping("/api")
public class ProdutoController {
    @GetMapping("/produtos")
    public List<Produto> listar() {
        return produtoService.listar();
    }
}
```

### 🗃 Spring Data JPA

- Mapeamento ORM com Hibernate
- Interfaces `JpaRepository`, `CrudRepository`

```java
public interface ProdutoRepository extends JpaRepository<Produto, Long> {}
```

### 🔐 Spring Security

- Autenticação e autorização com `HttpSecurity`
- Suporte a JWT, OAuth2, login básico e via formulário

### 📦 Validação

- Com `javax.validation` e anotações como `@NotNull`, `@Email`, `@Size`

---

## ⚙️ Configuração e Profiles

### application.properties ou application.yml

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/app
spring.datasource.username=root
spring.datasource.password=1234
server.port=8081
```

### Perfis de ambiente

```properties
# application-dev.properties
spring.jpa.show-sql=true
```

Ativando com:

```bash
--spring.profiles.active=dev
```

---

## ✅ Testes com Spring Boot

### Testes unitários

```java
@WebMvcTest(ProdutoController.class)
public class ProdutoControllerTest {
    @Autowired private MockMvc mockMvc;
}
```

### Testes de integração

```java
@SpringBootTest
@AutoConfigureMockMvc
public class ProdutoIntegrationTest {
    @Autowired private MockMvc mockMvc;
}
```

---

## 📁 Boas Práticas

- Separe bem as camadas: controller, service, repository, dto
- Use `@Service`, `@Repository`, `@RestController`
- Evite lógica de negócio em controllers
- Utilize DTOs para entrada e saída de dados
- Adote padrão de exceções com `@ControllerAdvice`

---

## 📚 Recursos Recomendados

- Documentação: [https://docs.spring.io/spring-boot](https://docs.spring.io/spring-boot)
- Livro: Spring in Action (Craig Walls)
- Cursos: Alura, Udemy, Digital Innovation One
