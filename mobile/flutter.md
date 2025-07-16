# 💙 Flutter

Flutter é um framework da Google para criação de aplicativos nativos multiplataforma (Android, iOS, Web e Desktop) usando uma única base de código em Dart.

---

## 🧱 Widgets

Tudo no Flutter é um widget:

- **StatelessWidget**: interface fixa.
- **StatefulWidget**: interface que muda com o tempo.
- Widgets de layout: `Column`, `Row`, `Stack`, `Container`.
- Widgets visuais: `Text`, `Image`, `Icon`, `ElevatedButton`.

Exemplo:
```dart
return Scaffold(
  appBar: AppBar(title: Text('Exemplo')),
  body: Center(child: Text('Olá, Flutter!')),
);
```
---

## 🧭 Navegação

Navigator.push(), pop(): empilha rotas manualmente.

named routes: rotas nomeadas e centralizadas.

go_router (recomendado): navegação declarativa moderna com deep linking.

Exemplo:

```dart
GoRouter(
  routes: [
    GoRoute(path: '/', builder: (context, state) => HomePage()),
    GoRoute(path: '/login', builder: (context, state) => LoginPage()),
  ],
);
```
---

## ⚙️ Gerenciamento de Estado

- **Provider: oficial e simples para apps menores.**

- **Riverpod: mais flexível, testável e escalável.**

- **Bloc/Cubit: baseado em streams e separação clara entre UI e lógica.**

- **Escolha baseada no tamanho e complexidade do app.**

---

## 🔗 Integração com APIs

Utilize http, dio ou retrofit para chamadas REST:

```dart
final response = await http.get(Uri.parse('https://api.exemplo.com/dados'));
```
Dicas:

Use model.fromJson para mapear dados.

Mantenha serviços desacoplados da UI.

---

## 🧪 Testes

- **Unitários: lógica pura (test package).**

- **Widgets: testa componentes visuais (flutter_test).**

- **Integração: usa integration_test + emuladores ou dispositivos reais.**

```dart
Copiar
Editar
test('soma simples', () {
  expect(1 + 2, 3);
});
```

---

## 📦 Publicação

- **Android: gere bundle (.aab) com flutter build appbundle.**

- **iOS: use Xcode para assinar e subir para App Store Connect.**

- **Configure ícones, splash, permissões (pubspec.yaml, AndroidManifest.xml, Info.plist).**

Flutter permite criar experiências fluidas com alta produtividade e um ecossistema em constante evolução.