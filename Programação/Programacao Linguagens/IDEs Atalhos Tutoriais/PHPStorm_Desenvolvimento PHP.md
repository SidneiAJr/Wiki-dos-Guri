# **Tutorial PHPStorm para Desenvolvimento PHP com Frameworks**

## 1. **Instalando o PHPStorm**

### Passo 1: Baixar o PHPStorm
- Acesse o site oficial: [PHPStorm](https://www.jetbrains.com/phpstorm/)
- Escolha a versão que se adapta ao seu sistema operacional (Windows, macOS, Linux).
- Faça o download e instale.

### Passo 2: Ativar a Licença
- O PHPStorm é pago, mas tem uma versão de teste de 30 dias. Se já tiver uma licença, basta inseri-la.
- Se não tiver, pode usar a versão trial para testar.

---

## 2. **Configuração Inicial do PHPStorm**

### Passo 1: Configurar o PHP Interpreter
1. Abra o **PHPStorm**.
2. Vá em `File > Settings` (ou `PHPStorm > Preferences` no macOS).
3. Na janela de configurações, vá em `Languages & Frameworks > PHP`.
4. Em "PHP", selecione o **Interpreter** (interprete) do PHP que você vai usar. Caso não tenha um configurado, adicione o caminho do PHP instalado no seu sistema.
   
   - No **Windows**, pode ser algo como `C:\xampp\php\php.exe`.
   - No **Linux/macOS**, geralmente é `/usr/bin/php` ou o caminho onde o PHP está instalado.

5. Clique em **Apply** e depois em **OK**.

### Passo 2: Configuração do Composer
- O **Composer** é essencial para gerenciar dependências de frameworks PHP como Laravel, Symfony, etc.
- Se você não tiver o **Composer** instalado, baixe e instale a partir de [aqui](https://getcomposer.org/download/).

No **PHPStorm**, você pode configurar o Composer para rodar diretamente da IDE:
1. Vá em `File > Settings > Languages & Frameworks > PHP > Composer`.
2. Selecione o caminho para o arquivo **composer.phar** ou o local do Composer globalmente instalado.

---

## 3. **Configurando um Projeto PHP com Framework**

### Passo 1: Criando um Novo Projeto PHP
1. Na tela inicial do PHPStorm, clique em `Create New Project`.
2. Selecione `PHP` no painel da esquerda e defina o local onde o projeto será salvo.
3. Escolha o **Framework** que você deseja (como Laravel, Symfony, etc.). Caso não esteja listado, você pode criar um projeto PHP "puro" e instalar o framework manualmente.

### Passo 2: Instalando um Framework com Composer
Por exemplo, se você quiser trabalhar com **Laravel**, basta:
1. Abra o terminal integrado no PHPStorm (`Alt + F12` ou `View > Tool Windows > Terminal`).
2. Execute o comando para instalar o Laravel:
   ```bash
   composer create-project --prefer-dist laravel/laravel nome-do-projeto
