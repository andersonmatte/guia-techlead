# 🍏 iOS Nativo

O desenvolvimento nativo para iOS oferece total controle sobre performance, design e recursos do ecossistema Apple.

---

## 🍎 Swift

- Linguagem moderna, segura e performática.
- Suporte a orientações funcional e orientada a objetos.
- Optionals, closures, generics e protocolo-oriented programming.

Exemplo:
```swift
let nome = "Anderson"
print("Olá, \(nome)!")
```
---

## 🧱 UIKit e SwiftUI

UIKit: tradicional, baseado em ViewControllers e Storyboards.

SwiftUI: declarativo, moderno, com preview em tempo real (iOS 13+).

SwiftUI exemplo:

```swift
var body: some View {
  Text("Bem-vindo ao SwiftUI")
    .font(.headline)
}
```

---

## 🧠 Gerenciamento de Memória

- **ARC (Automatic Reference Counting) cuida da alocação/desalocação.**

- **Evite retain cycles usando [weak self] em closures.**

- **Use instruments para detectar vazamentos de memória.**

---

## 🧰 Xcode e Provisionamento

- **Xcode: IDE oficial, com simuladores, depuração e storyboard editor.**

- **Assinatura digital via provisioning profiles.**

- **Gerencie certificados pelo Apple Developer Center.**

- **Exporte builds com Archive > Distribute App.**

*Checklist:*

- **Configurar Bundle ID e Signing.**

- **Usar TestFlight para testes internos.**

- **Subir para App Store Connect.**

iOS nativo exige atenção aos detalhes, mas permite criar experiências premium totalmente integradas ao ecossistema Apple.