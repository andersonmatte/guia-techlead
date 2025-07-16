# 🤖 Android Nativo

Desenvolvimento Android com Java ou Kotlin, explorando os principais recursos nativos da plataforma.

---

## ☕ Java / Kotlin

- **Java**: linguagem tradicional, ainda amplamente usada em projetos legados.
- **Kotlin**: linguagem moderna, oficial desde 2017, com foco em concisão, segurança e interoperabilidade com Java.

Exemplo Kotlin:
```kotlin
val nome = "Anderson"
println("Olá, $nome!")
```

---

## 🔁 Ciclo de Vida

Cada Activity e Fragment tem um ciclo de vida controlado pelo sistema Android.

Principais métodos:

- **onCreate(): inicialização.**

- **onStart() / onResume(): visível para o usuário.**

- **onPause() / onStop(): app em background.**

- **onDestroy(): liberação de recursos.**

Use ViewModel + LiveData para preservar estado.

---

## 🧰 Jetpack Components
Conjunto de bibliotecas modernas para acelerar o desenvolvimento:

- **ViewModel: separa lógica de UI.**

- **LiveData: reatividade com ciclo de vida.**

- **Navigation Component: navegação declarativa entre telas.**

- **Room: persistência local com SQLite.**

*Boas práticas:*

Use ViewModelProvider para injetar ViewModels.

Centralize navegação com nav_graph.xml.

---

## ⚙️ Gradle e Build

O Gradle é o sistema de build do Android.

Configuração em build.gradle.

Modularização: organize o app em módulos (:app, :core, :feature-login).

Use buildTypes (debug, release) e flavors (free, paid).

Exemplo:

```groovy
buildTypes {
    release {
    minifyEnabled true
    proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
    }
}
```
O desenvolvimento nativo oferece controle total, mas exige atenção especial à compatibilidade, gestão de recursos e performance.