#  Flutter | Tipos de Entrada de Texto no Flutter

No Flutter, o widget **TextField** é usado para criar campos de entrada de texto. Ele pode ser configurado de várias maneiras para atender a diferentes necessidades de entrada do usuário. Abaixo, são apresentados os principais tipos de entrada de texto que você pode criar em Flutter.

## **Entrada de Texto Simples**

Um campo de texto básico para o usuário digitar informações.

```dart
TextField(
  decoration: InputDecoration(
    labelText: 'Digite algo',
  ),
)
````
- Permite digitar texto simples.

- Pode ser estilizado com decoration.

## Entrada de Texto com Controlador

Você pode usar o TextEditingController para capturar e manipular o texto digitado pelo usuário.

```dart
final TextEditingController controller = TextEditingController();

TextField(
  controller: controller,
  decoration: InputDecoration(
    labelText: 'Digite seu nome',
  ),
)
````

- Permite acessar e modificar o texto programaticamente.

- Ideal para quando você precisa recuperar ou alterar o conteúdo do campo de texto.

## Entrada de Texto com Senha

Para campos de senha, você pode ocultar o texto enquanto o usuário digita.
```dart
TextField(
  obscureText: true,  // Oculta o texto
  decoration: InputDecoration(
    labelText: 'Digite sua senha',
  ),
)
```

## Entrada de Texto com Validação

Você pode adicionar validação ao campo de texto para garantir que a entrada seja válida.
```dart
final GlobalKey<FormState> _formKey = GlobalKey<FormState>();

Form(
  key: _formKey,
  child: TextFormField(
    decoration: InputDecoration(
      labelText: 'Digite seu email',
    ),
    validator: (value) {
      if (value == null || value.isEmpty) {
        return 'Campo obrigatório';
      }
      return null;
    },
  ),
)
````

## Entrada de Texto com Máscara (Formatação)

É possível aplicar uma máscara para formatar o texto enquanto o usuário digita, como para números de telefone ou CPF.

```dart
import 'package:flutter_masked_text/flutter_masked_text.dart';

var phoneController = MaskedTextController(mask: '(000) 000-0000');

TextField(
  controller: phoneController,
  decoration: InputDecoration(
    labelText: 'Digite seu telefone',
  ),
)
```

## Entrada de Texto Multilinhas

Para permitir que o usuário digite várias linhas de texto (ex: mensagens ou descrições), você pode usar a propriedade maxLines.

```dart
TextField(
  maxLines: 5,
  decoration: InputDecoration(
    labelText: 'Digite sua mensagem',
  ),
)
```

## Entrada de Texto com Auto-Correção

Para permitir que o usuário digite várias linhas de texto (ex: mensagens ou descrições), você pode usar a propriedade maxLines.

```dart
TextField(
  maxLines: 5,
  decoration: InputDecoration(
    labelText: 'Digite sua mensagem',
  ),
)
```

## Entrada de Texto com Auto-Correção

Você pode ativar ou desativar a correção automática e outras sugestões de texto.

```dart

TextField(
  autocorrect: true,  // Ativa a correção automática
  decoration: InputDecoration(
    labelText: 'Digite algo com correção',
  ),
)
```

## Entrada de Texto com Sugestões de Completamento

Para campos de texto que sugerem opções para o usuário, você pode usar o TextField com sugestões de autocomplete.

```dart
TextField(
  decoration: InputDecoration(
    labelText: 'Digite o nome da cidade',
    hintText: 'Ex: São Paulo',
  ),
  onChanged: (text) {
    // Ações baseadas na entrada
  },
)
```




