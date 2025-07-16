# ☕ Java — Guia Completo para Backend

Este documento é uma base sólida para desenvolvedores backend que utilizam Java em ambientes profissionais.

---

## 📦 Ambiente e Ferramentas

### 🧰 Ferramentas Essenciais

- **JDK (Java Development Kit)**: Baixe a versão mais recente do [site oficial](https://jdk.java.net/) ou distribuições como OpenJDK, Oracle JDK, Amazon Corretto, Azul Zulu.
- **IDE recomendadas**:
  - **IntelliJ IDEA** (versão Community ou Ultimate)
  - Eclipse
  - VSCode com extensão Java
- **Gerenciadores de build**:
  - **Maven** (pom.xml)
  - **Gradle** (build.gradle.kts)

### ✅ Configuração do Ambiente

- Variável `JAVA_HOME`
- Verificação com `java -version` e `javac -version`
- Ferramentas de versionamento Java: `SDKMAN!`, `JEnv`

---

## 📘 Sintaxe Essencial

### Estrutura de um programa básico

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Olá, mundo!");
    }
}
```

### Tipos de dados primitivos

- int, double, boolean, char, long, float, byte, short

### Controle de fluxo

- Condicionais: `if`, `else`, `switch`
- Loops: `for`, `while`, `do-while`, `for-each`

### Arrays e Strings

- Manipulação de arrays com `for` e `Arrays.stream`
- Strings são objetos imutáveis

---

## 🔑 Programação Orientada a Objetos (OOP)

### Pilares da OOP

1. **Encapsulamento**
2. **Herança**
3. **Polimorfismo**
4. **Abstração**

### Classes, Objetos e Métodos

```java
public class Pessoa {
    private String nome;
    public Pessoa(String nome) {
        this.nome = nome;
    }
    public void dizerOla() {
        System.out.println("Olá, " + nome);
    }
}
```

### Interfaces e Classes Abstratas

- Interfaces definem contratos
- Classes abstratas contêm implementação parcial

---

## 🧰 Collections, Streams e Lambdas

### Coleções mais usadas

- List, Set, Map
- Implementações: ArrayList, HashSet, HashMap

### Exemplo de uso de `List` com Lambda e Stream API

```java
List<String> nomes = Arrays.asList("Ana", "Bruno", "Carlos");
nomes.stream()
     .filter(nome -> nome.startsWith("A"))
     .forEach(System.out::println);
```

### Operações comuns com Stream API

- `map()`, `filter()`, `collect()`, `sorted()`, `reduce()`

---

## ✨ Boas Práticas em Java

### Clean Code

- Nomeie variáveis de forma descritiva
- Métodos devem ter uma única responsabilidade
- Evite efeitos colaterais ocultos

### SOLID

- **S**: Single Responsibility Principle
- **O**: Open/Closed Principle
- **L**: Liskov Substitution Principle
- **I**: Interface Segregation Principle
- **D**: Dependency Inversion Principle

### Convensões e Estilo

- CamelCase para variáveis e métodos
- PascalCase para classes
- Use `final` para constantes e imutabilidade

---

## 📚 Recursos Recomendados

- Livro: Effective Java (Joshua Bloch)
- Curso: Java Programming (Alura, Udemy, Coursera)
- Documentação oficial: https://docs.oracle.com/en/java/
