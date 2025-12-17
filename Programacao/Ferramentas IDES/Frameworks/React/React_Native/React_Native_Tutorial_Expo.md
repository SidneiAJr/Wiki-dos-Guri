# Tutorial Básico de React Native com Expo

Esse tutorial vai te guiar na criação do seu primeiro aplicativo React Native utilizando o **Expo**. O **Expo** facilita o processo de desenvolvimento, sem a necessidade de configuração de emuladores ou complicação com dependências nativas. Vamos criar um contador simples com botão.

---

## 1. **Instalação do Ambiente**

Antes de começar a codificar, você precisa ter algumas ferramentas instaladas no seu computador.

### Passo 1: Instalar o **Node.js**
1. Acesse o [site oficial do Node.js](https://nodejs.org) e baixe a versão **LTS**.
2. Siga o instalador e verifique se o Node.js foi instalado corretamente rodando no terminal:
```bash
   node -v
   npm -v
```

Passo 2: Instalar o Expo CLI

O Expo CLI é uma ferramenta de linha de comando que facilita a criação e o gerenciamento de aplicativos React Native.

Abra o terminal e rode o seguinte comando:

```bash
npm install -g expo-cli
```

Baixe o app Expo Go na App Store (para iOS) ou Google Play (para Android). Com esse app, você poderá visualizar seu aplicativo React Native no celular, escaneando o QR code gerado pelo Expo.
```bash
expo init MeuPrimeiroApp
```

## Exemplo de Codigo:

```React
import React from 'react';
import { StyleSheet, Text, View, Button } from 'react-native';

export default function App() {
  const [count, setCount] = React.useState(0);

  return (
    <View style={styles.container}>
      <Text style={styles.title}>Contador React Native</Text>
      <Text style={styles.counter}>{count}</Text>
      <Button title="Incrementar" onPress={() => setCount(count + 1)} />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#fff',
  },
  title: {
    fontSize: 24,
    fontWeight: 'bold',
  },
  counter: {
    fontSize: 48,
    marginVertical: 20,
  },
});
```
