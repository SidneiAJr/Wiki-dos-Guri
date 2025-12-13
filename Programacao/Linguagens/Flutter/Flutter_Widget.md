# Flutter | Widgets Básicos e Layouts

## 1. Widgets Básicos do Flutter

No Flutter, os widgets são os blocos fundamentais para construir interfaces de usuário. Existem muitos tipos de widgets, mas vamos começar com os mais básicos.

### 1.1 **`Text`**
O widget **`Text`** é usado para exibir uma sequência de texto.

#### Exemplo:
```dart
Text(
  'Olá, Flutter!',
  style: TextStyle(fontSize: 24, color: Colors.blue),
)
```

## Container

O Container é um widget básico que pode ser usado para criar caixas, adicionar margens, padding, bordas, etc.

```dart
Container(
  width: 200,
  height: 100,
  color: Colors.blue,
  child: Center(
    child: Text(
      'Dentro do Container',
      style: TextStyle(color: Colors.white),
    ),
  ),
)
```

## Column e Row

Column organiza os widgets verticalmente.

Row organiza os widgets horizontalmente.

```dart
Column(
  children: <Widget>[
    Text('Primeiro'),
    Text('Segundo'),
    Text('Terceiro'),
  ],
)
```

## Expanded

O Expanded é usado dentro de um Column ou Row para fazer um widget ocupar o máximo de espaço disponível.

```dart
Row(
  children: <Widget>[
    Icon(Icons.access_alarm),
    Expanded(
      child: Text('Texto expansível'),
    ),
    Icon(Icons.accessibility),
  ],
)
```

## Stack

O widget Stack permite sobrepor widgets. Você pode empilhar widgets uns sobre os outros.

```dart
Stack(
  children: <Widget>[
    Container(
      width: 200,
      height: 200,
      color: Colors.blue,
    ),
    Positioned(
      top: 50,
      left: 50,
      child: Text('Texto sobre a caixa'),
    ),
  ],
)
```



