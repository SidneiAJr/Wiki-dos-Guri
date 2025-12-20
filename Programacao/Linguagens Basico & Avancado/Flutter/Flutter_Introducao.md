# Flutter | Introdução ao Flutter

**Flutter** é um framework de desenvolvimento de UI (Interface de Usuário) de código aberto criado pelo Google, que permite criar aplicações nativas compiladas para dispositivos móveis (iOS e Android), web e desktop a partir de uma única base de código. Com Flutter, é possível construir interfaces ricas, rápidas e responsivas, utilizando a linguagem de programação Dart.

## Índice

1. [O que é o Flutter?](#o-que-é-o-flutter)
2. [Vantagens do Flutter](#vantagens-do-flutter)
3. [Instalação do Flutter](#instalacao-do-flutter)
4. [Primeiro Projeto no Flutter](#primeiro-projeto-no-flutter)
5. [Estrutura de um Projeto Flutter](#estrutura-de-um-projeto-flutter)
6. [Widgets no Flutter](#widgets-no-flutter)
7. [Hot Reload](#hot-reload)
8. [Próximos Passos](#proximos-passos)

## O que é o Flutter?

Flutter é um framework de UI que permite construir aplicativos nativos para várias plataformas (Android, iOS, Web, e Desktop) a partir de uma única base de código. Ao invés de usar componentes nativos, o Flutter oferece seus próprios widgets que são desenhados de forma rápida e eficiente.

Flutter usa a linguagem **Dart**, desenvolvida pelo Google, que foi projetada para ser eficiente e fácil de aprender.

### Principais características do Flutter:
- **Desempenho nativo**: Flutter compila o código para código nativo de cada plataforma, o que resulta em desempenho muito rápido.
- **Desenvolvimento multiplataforma**: Com uma única base de código, você pode gerar aplicativos para Android, iOS, Web e Desktop.
- **Interface rica e personalizável**: O Flutter oferece uma vasta coleção de widgets e facilita a criação de interfaces personalizadas.

## Vantagens do Flutter

- **Desenvolvimento rápido**: Com o Flutter, você pode criar e testar rapidamente sua aplicação, graças ao recurso de *Hot Reload*.
- **Desempenho elevado**: O Flutter usa a linguagem Dart, que compila para código nativo, proporcionando excelente desempenho.
- **Comunidade ativa**: A comunidade do Flutter tem crescido rapidamente, com muitas bibliotecas e pacotes sendo desenvolvidos constantemente.
- **Personalização de UI**: O Flutter permite personalizar todos os aspectos da interface do usuário, desde os widgets até a animação.

## Instalação do Flutter

Antes de começar a criar seu projeto Flutter, você precisa instalar o Flutter em sua máquina. O processo varia de acordo com o sistema operacional que você está utilizando.

### Para Windows, macOS ou Linux:
1. Acesse o site oficial do Flutter: [Flutter - Get Started](https://flutter.dev/docs/get-started/install)
2. Selecione seu sistema operacional e siga as instruções para baixar o SDK do Flutter.
3. Após o download, extraia o arquivo e adicione o diretório do Flutter ao **PATH** para poder executá-lo no terminal.

### Verificação da instalação:
Após a instalação, você pode verificar se o Flutter foi instalado corretamente executando o seguinte comando no terminal:

- flutter create meu_primeiro_app
- cd meu_primeiro_app
- flutter run

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text("Meu Primeiro App"),
        ),
        body: Center(
          child: Text("Olá, Flutter!"),
        ),
      ),
    );
  }
}
````


```bash
flutter doctor
````
