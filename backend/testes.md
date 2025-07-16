# ✅ Testes Backend

Este documento descreve as principais práticas e tecnologias para testes no backend, com foco em aplicações Java, utilizando JUnit 5, Mockito, Testcontainers e análise de cobertura de código.

---

## 🧪 JUnit 5 e Mockito

### JUnit 5

JUnit 5 é o framework padrão para testes unitários em aplicações Java modernas. Ele introduz uma arquitetura modular com os seguintes componentes:

- **JUnit Platform**: base para execução de testes.
- **JUnit Jupiter**: API para escrever testes e extensões.
- **JUnit Vintage**: suporte a testes legados (JUnit 3 e 4).

**Exemplo simples com JUnit 5:**

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

class CalculadoraTest {

    @Test
    void testSoma() {
        Calculadora calc = new Calculadora();
        assertEquals(5, calc.somar(2, 3));
    }
}
```

### Mockito

Mockito é um framework de mocking para Java que permite criar objetos simulados (mocks) para isolar a unidade de código em teste.

- **Exemplo com Mockito:**

```java
import static org.mockito.Mockito.*;
import org.junit.jupiter.api.Test;

class ServicoTest {

    @Test
    void testComMock() {
        Repositorio repo = mock(Repositorio.class);
        when(repo.getDado()).thenReturn("valor simulado");

        Servico servico = new Servico(repo);
        assertEquals("valor simulado", servico.obterValor());
    }
}
```
---

## ⚔️ Testes Unitários vs Testes de Integração

| Aspecto              | Teste Unitário                      | Teste de Integração                             |
|----------------------|-------------------------------------|-------------------------------------------------|
| Escopo               | Método ou classe isolada            | Conjunto de componentes/sistemas                |
| Dependências externas| Simuladas (mocks/stubs)             | Reais (banco, APIs, etc.)                       |
| Velocidade           | Muito rápido                        | Mais lento                                      |
| Confiabilidade       | Alta (isolamento)                   | Média (possibilidade de falhas externas)        |
| Objetivo             | Verificar lógica de negócio         | Verificar integração entre componentes          |


*É recomendável adotar ambos os tipos para garantir qualidade e confiança no sistema.*

### 🐳 Testcontainers
Testcontainers é uma biblioteca Java que fornece instâncias de containers Docker para testes de integração com recursos externos como banco de dados, mensageria, etc.

Vantagens:

- **Ambientes reais durante os testes.**

- **Fácil integração com JUnit 5.**

- **Evita dependência de ambientes locais.**

Exemplo com PostgreSQL:

```java
import org.testcontainers.containers.PostgreSQLContainer;
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

class BancoDeDadosTest {

    @Test
    void testComPostgresContainer() {
        try (PostgreSQLContainer<?> postgres = new PostgreSQLContainer<>("postgres:14")) {
            postgres.start();

            String jdbcUrl = postgres.getJdbcUrl();
            String user = postgres.getUsername();
            String pass = postgres.getPassword();

            // Realizar testes de conexão e persistência aqui
        }
    }
}
```
---

### 📊 Cobertura de Código

Cobertura de código (Code Coverage) mede o quanto do código-fonte é exercitado durante a execução dos testes. As principais métricas são:

- **Line Coverage: percentual de linhas executadas.**

- **Branch Coverage: percentual de ramificações (if/else, switch) exercitadas.**

- **Method Coverage: percentual de métodos chamados nos testes.**

Ferramentas populares:

- **JaCoCo (Java Code Coverage): plugin de fácil integração com Maven e Gradle.**

- **SonarQube: análise de qualidade e cobertura integrada.**

Exemplo de configuração no pom.xml:

```xml
<plugin>
  <groupId>org.jacoco</groupId>
  <artifactId>jacoco-maven-plugin</artifactId>
  <version>0.8.8</version>
  <executions>
    <execution>
      <goals>
        <goal>prepare-agent</goal>
      </goals>
    </execution>
    <execution>
      <id>report</id>
      <phase>verify</phase>
      <goals>
        <goal>report</goal>
      </goals>
    </execution>
  </executions>
</plugin>
```
---

### 🎯 Objetivo recomendado: atingir pelo menos 80% de cobertura, sem esquecer da qualidade dos testes — cobertura não significa ausência de bugs.

### ✅ Conclusão
O uso combinado de JUnit 5, Mockito, Testcontainers e análise de cobertura de código fortalece a confiabilidade do backend, assegura regressões controladas e mantém a manutenibilidade do sistema.

A adoção dessas práticas deve ser contínua e integrada ao processo de CI/CD para garantir entregas com qualidade desde o desenvolvimento até a produção.