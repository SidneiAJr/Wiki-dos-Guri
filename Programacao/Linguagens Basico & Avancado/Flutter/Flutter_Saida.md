# Flutter | Saídas

No Flutter, as saídas são geradas através de widgets que exibem informações ou reagem à entrada do usuário. Esses widgets podem ser texto, imagens, listas, ou qualquer outro tipo de componente visual que mostre dados para o usuário. 

Aqui, vamos explorar os principais tipos de **saídas** no Flutter.

---

##  **Texto: Exibindo Informações com `Text`**

O widget mais comum para exibir texto no Flutter é o **`Text`**. Ele permite mostrar dados simples ou dinâmicos de uma forma clara e customizável.

### Exemplo:
```dart
Text(
  'Olá, Flutter!',
  style: TextStyle(
    fontSize: 24,
    color: Colors.blue,
  ),
)
```

## Caixas de Diálogo (Dialogs)

```dart
showDialog(
  context: context,
  builder: (BuildContext context) {
    return AlertDialog(
      title: Text('Atenção'),
      content: Text('Deseja sair da aplicação?'),
      actions: <Widget>[
        TextButton(
          child: Text('Cancelar'),
          onPressed: () {
            Navigator.of(context).pop();
          },
        ),
        TextButton(
          child: Text('Sim'),
          onPressed: () {
            Navigator.of(context).pop();
            // Ação para sair
          },
        ),
      ],
    );
  },
);
````

## Saídas de Texto com Formatação: RichText

````dart
RichText(
  text: TextSpan(
    text: 'Flutter ',
    style: TextStyle(fontSize: 24, color: Colors.blue),
    children: <TextSpan>[
      TextSpan(
        text: 'é incrível!',
        style: TextStyle(fontWeight: FontWeight.bold, color: Colors.orange),
      ),
    ],
  ),
)
````

