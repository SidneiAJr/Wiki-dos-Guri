## PHP | `Sistema de Cadastro Medico` | `Listagem` |` Exclusão` | `Menu Administrativo`

### Observações Minha em 2025(`So eu e deus Lembravam- Nem Ele Lembra Muito menos eu`)
- Este sistema foi originalmente feito entre 2014 e 2016.
- Muitos trechos tinham mistura de "alunos" e "médicos" por causa de reciclagem de código.
- Esta documentação serve para lembrar a estrutura original antes da refatoração.
- Código legado preservado apenas para nostalgia e referência.


## Banco de Dados Clinica:

### `Tabela |Especialização:`

````SQl
CREATE TABLE especialidades (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL
);
````
### `Tabela | Medicos:`

````SQl
CREATE TABLE medicos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    crm VARCHAR(20) NOT NULL,
    dt_nascimento DATE NOT NULL,
    especialidade_id INT NOT NULL,
    foto VARCHAR(200),
    FOREIGN KEY (especialidade_id) REFERENCES especialidades(id)
);
````

### `Tabela | Usuarios:`
````SQl
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    usuario VARCHAR(50) NOT NULL UNIQUE,
    senha VARCHAR(255) NOT NULL

INSERT INTO usuarios (usuario, senha)
VALUES ('admin', MD5('123'));
);
````



### `Tabela | Medico Especialidade:`
````SQl
CREATE TABLE medico_especialidade (
    id INT AUTO_INCREMENT PRIMARY KEY,
    medico_id INT NOT NULL,
    especialidade_id INT NOT NULL,
    FOREIGN KEY (medico_id) REFERENCES medicos(id),
    FOREIGN KEY (especialidade_id) REFERENCES especialidades(id)
);
````

## Formulário de Especialidade - HTML

## Descrição
Este código HTML contém um formulário simples para a entrada de dados de especialidade. O usuário pode inserir uma especialidade e enviar o valor para o script `incESP.php` via método `POST`.

## Fluxo do Código

1. O código apresenta um formulário com um campo de texto para o usuário digitar a especialidade.
2. O campo tem o nome `f_especialidade`, e o valor inserido será enviado para o script PHP `incESP.php` quando o formulário for submetido.
3. O formulário não possui botão de envio visível, o que significa que o envio do formulário pode ser feito por outro mecanismo (ex: JavaScript ou ação de outro elemento).

## Código HTML

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Documento sem título</title>
</head>

<body>
<form id="form1" name="form1" method="post" action="incESP.php">
  Especialidade 
  <label for="f_especialidade"></label>
  <input name="f_especialidade" type="text" id="f_especialidade" size="50" maxlength="50" />
</form>
</body>
</html>

````

## Formulário de Cadastro de Médico

## Descrição
Este código HTML cria um formulário simples para cadastrar informações sobre um médico. O formulário coleta dados como nome, CRM, data de nascimento, especialidade e foto. O formulário usa o método `POST` para enviar os dados, incluindo a capacidade de fazer upload de um arquivo de imagem (foto).

## Fluxo do Código

1. O formulário coleta as informações do usuário.
2. Ele possui campos de texto para o nome, CRM e data de nascimento.
3. Há um menu suspenso (`<select>`) para escolher a especialidade do médico.
4. O formulário permite o upload de uma foto do médico.
5. Ao final, o usuário pode enviar o formulário ou resetá-lo.

## Código HTML

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Documento sem título</title>
</head>

<body>
<form action="" enctype="multipart/form-data" method="post">
  <p>Nome:</p>
  <p>
    <label for="f_nome"></label>
    <input name="f_nome" type="text" id="f_nome" size="50" />
    <br />
  </p>
  <p>Crm<br />
    <label for="f_crm"></label>
    <input name="f_crm" type="text" id="f_crm" size="10" />
  </p>
  <p>Dt nascimento</p>
  <p>
    <label for="f_dtnasc"></label>
    <input name="f_dtnasc" type="text" id="f_dtnasc" size="10" />
  </p>
  <p>Especialidade</p>
  <p>
    <select name="f_especialidade" id="f_especialidade">
      <option value="1">Pediatria</option>
      <option value="2">Clínico Geral</option>
      <option value="3">Cardiologista</option>
      <option value="4">Neurologista</option>
    </select>
  </p>
  <p>Foto</p>
  <p>
    <label for="f_foto"></label>
    <input type="file" name="f_foto" id="f_foto" />
    <br />
    <input type="submit" value="Incluir" />
    <input type="reset" value="Limpar" />
  </p>
</form>
</body>
</html>

```

## Código PHP - Atualização e Exibição de Dados de Médicos

## Descrição

Este código PHP gerencia a atualização de dados de médicos na base de dados. Ele inclui:
1. **Exibição de uma lista de médicos**.
2. **Atualização dos dados do médico** com base em um ID fornecido.
3. **Envio de uma foto** de perfil para o médico (somente se for do tipo `.jpeg`).
4. **Verificação e validação** dos dados inseridos, como se o ID é válido e se o formato da foto está correto.

## Fluxo do Código

1. **Verificação de Sessão**: O código começa verificando se o usuário está logado. Se não, ele é redirecionado para uma página de erro.
2. **Consulta ao Banco de Dados**: O código consulta os dados dos médicos através de um `SELECT` e exibe uma lista deles.
3. **Validação de Parâmetros**: O código verifica se o parâmetro `codigo` foi passado corretamente na URL. Se o parâmetro não for numérico ou não for informado, uma mensagem de erro é exibida.
4. **Atualização de Dados**: Se o médico existir, o código atualiza as informações, como o nome e CRM. Além disso, ele pode substituir a foto atual do médico.
5. **Conclusão**: Após as alterações, o código exibe uma mensagem confirmando o sucesso da operação e exibe a lista atualizada de médicos.

## Código PHP

```php
<?php
session_start();
if($_SESSION['loginok'] != 'ok') {
    header('location:erro.html');
}
?>
```

```html

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>index</title>
</head>

<body>
<p>
```

```php
<?php
include "conexao.php";
$sql = "SELECT codigo, crm FROM medicos ORDER BY nome";
$res = mysqli_query($conexao, $sql) or die("Falha ao selecionar!");
$total = mysqli_num_rows($res);
if ($total == 0) {
    echo "<b>Nenhum</b> aluno encontrado!";
} else {
    while ($linha = mysqli_fetch_row($res)) {
        $idaluno = $_GET["codigo"];
        if (!isset($idaluno)) {
            echo "Aluno não informado!";
        } else {
            if (!is_numeric($idaluno)) {
                echo "Parâmetro inválido!";
            } else {
                include "../atv3/conexao.php";
                $sql = "SELECT * FROM alunos WHERE id = $idaluno";
                $res = mysqli_query($conexao, $sql) or die("Erro ao selecionar código!");
                $total = mysqli_num_rows($res);
                if ($total == 0) {
                    echo "Médico não localizado!";
                } else {
                    $mnome = $_POST["f_codigo"];
                    $mnivel = $_POST["f_crm"];
                    $erro = false;
                    if (empty($mnome)) {
                        echo "<b>NOME</b> não informado!";
                        $erro = true;
                    }
                    if ($erro) {
                        echo "<br>O formulário apresenta erros, favor corrigir...";
                    } else {
                        include "../a1/conexao.php";
                        $sql = "UPDATE medicos SET nome = '$mnome', nivel = $mnivel WHERE id = $idaluno";
                        mysqli_query($conexao, $sql) or die("Erro na atualização de dados!");
                        echo "<b>Aluno</b> atualizado com sucesso!";
                    }
                }
            }
        }
        $foto = $_FILES["f_foto"];
        if (!empty($foto["name"])) {
            if ($foto["type"] != 'image/jpeg') {
                echo "<b>Formato de arquivo inválido! Necessário .JPEG </b>";
            } else {
                $arquivo = "imagens/" . $idaluno . ".jpg";
                if (file_exists($arquivo)) {
                    unlink($arquivo);
                }
                move_uploaded_file($foto["tmp_name"], $arquivo);
                echo "<b>Foto inserida com sucesso!</b><br>";
            }
        } else {
            echo "<b>Nenhuma foto enviada</b><br>";
        }
    }
}
mysqli_close($conexao);
?>
</p>
```
```html
<table width="712" height="93" border="2">
    <tr>
        <td width="182" rowspan="2"><img src="Imagens/1.jpg" width="194" height="129" /></td>
        <td width="512">Livraria Paluminio</td>
    </tr>
    <tr>
        <td>
            <form id="form2" name="form2" method="post" action="">
                <p><strong>Usuário:
                    <label for="f_usuario"></label>
                    <input type="text" name="f_usuario" id="f_usuario" />
                </strong></p>
                <p><strong>Senha:
                    <label for="f_senha"></label>
                    <input name="f_senha" type="password" id="f_senha" />
                </strong>
                <input type="submit" name="button2" id="button2" value="Ok" />
                </p>
            </form>
        </td>
    </tr>
    <tr>
        <td rowspan="2">
            <form id="form1" name="form1" method="post" action="">
                <strong>Busca:
                    <label for="f_prod"></label>
                    <input type="text" name="f_prod" id="f_prod" />
                </strong>
                <input type="submit" name="button" id="button" value="Ok" />
            </form>
        </td>
        <td>
            <a href="../a1/exc_aluno.php?cod=<?php echo $linha[0]; ?>">Excluir</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="alt_aluno.php?cod=<?php echo $linha[0]; ?>"><img src="../atv3/imagens/pencil.png" width="16" height="16" border="0" /></a>
        </td>
    </tr>
</table>

<p><?php echo $linha[1]; ?></p>

<table width="711" height="181" border="2">
    <tr>
        <td>
            <div id="menu">
                <ul id="menu">
                    <li><a href="../atv3/lisamed.php">Listar Todos os Médicos</a><br /><br /></li>
                    <li><a href="../atv3/incmed.php?n=1">Incluir Novo Médico</a><br /><br /></li>
                    <li><a href="../atv3/adm_med.php?n=2">Administrar Médicos</a><br /><br /></li>
                    <li><a href="../atv3/incesp.php?n=3">Incluir Especialidade</a><br /><br /></li>
                    <li><a href="../atv3/adm_esp.php?n=3">Administrar Especialidades</a><br /><br /></li>
                </ul>
            </div>
            <a href="../atv2/index.html">Retornar</a>
        </td>
    </tr>
</table>
</body>
</html>

````

## Código PHP - Listagem de Médicos

## Descrição
Este código PHP se conecta a um banco de dados MySQL para listar médicos de uma clínica. Ele permite:
1. **Exibir a lista de médicos**.
2. **Filtrar a lista por nome**, se fornecido.
3. **Exibir informações detalhadas sobre os médicos**, como código, nome, CRM, data de nascimento e especialidade.

## Fluxo do Código

1. **Conexão com o Banco de Dados**: O código se conecta ao banco de dados MySQL chamado `clinicadodb` na máquina local.
2. **Consulta ao Banco**:
   - Se o código de busca (parâmetro `n`) for fornecido, ele faz uma consulta para listar médicos com base no nível especificado.
   - Se uma busca for feita via o campo de texto (parâmetro `f_busca`), ele faz uma busca baseada no nome.
   - Caso contrário, ele lista todos os médicos da base de dados.
3. **Exibição dos Dados**: O código exibe os dados dos médicos em uma tabela HTML.
4. **Erro de Conexão ou Dados Não Encontrados**: Mensagens de erro são exibidas se não houver médicos encontrados ou se houver falha na consulta ao banco de dados.

## Código PHP

```php
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>ListaMed</title>
</head>

<body>
<?php
    $conexao = mysqli_connect("localhost", "root", "") or die("Falha ao conectar com MySQL");
    $bd = mysqli_select_db($conexao, "clinicadodb") or die("Falha ao selecionar banco de dados - clinicadodb");

    // Recebe o parâmetro 'n' para consulta
    $codigo = $_GET["n"];
    
    // Verifica se o parâmetro 'codigo' foi passado
    if(isset($codigo)) {
        $sql = "SELECT codigo, medico, crm, dt_nascimento, especialidade FROM alunos WHERE nivel = $nivel ORDER BY nome";
    } else {
        $busca = $_POST["f_busca"];
        
        // Verifica se o campo de busca foi preenchido
        if(isset($busca)) {
            $sql = "SELECT codigo, medico, crm, dt_nascimento, especialidade FROM alunos WHERE nome LIKE '%".$codigo."%' ORDER BY codigo";   
        } else {
            // Caso não tenha filtro, lista todos os médicos
            $sql = "SELECT codigo, medico, crm, dt_nascimento, especialidade FROM clinicadodb ORDER BY codigo";
        }
    }
    
    // Executa a consulta ao banco de dados
    $res = mysqli_query($conexao, $sql) or die("Falha ao selecionar médicos!");
    $total = mysqli_num_rows($res);

    // Verifica se médicos foram encontrados
    if($total == 0) {
        echo "<b>Nenhum médico encontrado</b>";
    } else {
        // Exibe as informações dos médicos
        while($linha = mysqli_fetch_row($res)) {
?>
<table width="456" height="283" border="1">
  <tr>
    <td width="200"><img src="Imagens/1.jpg" width="195" height="151" /></td>
    <td colspan="2">CLÍNICA MÉDICA - MENU INICIAL</td>
  </tr>
  <tr>
    <td>Código</td>
    <td width="100">&nbsp;</td>
    <td width="134" rowspan="5">Imagem do paciente!</td>
  </tr>
  <tr>
    <td>Médico</td>
    <td>&nbsp;</td>
  </tr>
  <tr>
    <td>CRM</td>
    <td>&nbsp;</td>
  </tr>
  <tr>
    <td>Data de Nascimento</td>
    <td>&nbsp;</td>
  </tr>
  <tr>
    <td>Especialidade</td>
    <td>&nbsp;</td>
  </tr>
</table>
<p>
<?php
        }
    }
    mysqli_close($conexao);
?>
  
<p><a href="index.html">Retornar</a></p>
</body>
</html>

````

## Código PHP - Menu Administrativo da Clínica Médica

## Descrição

Este código HTML exibe um menu administrativo de uma clínica médica. Ele inclui a exibição de informações do médico, links para excluir o médico, adicionar especialidades, e retornar ao menu principal.

## Fluxo do Código

1. **Exibição de Dados**: O código exibe a imagem e o nome do médico na interface.
2. **Exclusão do Médico**: Há um link para excluir o médico, que é confirmado por um **JavaScript** antes de ser realizado.
3. **Incluir Especialidade**: Há um link para adicionar uma especialidade ao médico.
4. **Retornar ao Menu**: O código inclui um link para retornar ao menu principal do administrador.

## Código HTML

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Documento sem título</title>
</head>

<body>
<table width="420" height="195" border="1">
  <tr>
    <td width="200"><img src="Imagens/avatar.png" width="149" height="143" /></td>
    <td width="112">CLÍNICA MÉDICA AVALIA MENU ADMINISTRATIVO</td>
    <td width="86">&nbsp;</td>
  </tr>
  <tr>
    <td>Nome do médico</td>
    <td><a href="exc_aluno.php?cod=<?php echo $linha[0];?>" onclick="javascript:return confirmaExclusaoRegistro();">Excluir</a>&nbsp;</td>
    <td><a href="imagens/<?php echo $linha[0];?>.jpg" width="158" height="197" alt="" /></td>
  </tr>
  <tr>
    <td><a href="form_inc_esp.php">Incluir especialidade</a></td>
    <td><a href="menuadm.php">Retornar</a></td>
    <td>&nbsp;</td>
  </tr>
</table>
</body>
</html>

````

## Código PHP - Menu de Médicos Administrativos

## Descrição

Este código PHP exibe um menu administrativo para a gestão de médicos. Ele permite a **exclusão**, **edição** e **inclusão** de médicos no sistema. O código inclui os seguintes recursos:
1. **Exibição do nome do médico**.
2. **Link para excluir médico**.
3. **Link para editar os dados do médico**.
4. **Link para incluir um novo médico**.
5. **Link para retornar ao menu principal**.

## Fluxo do Código

1. **Exibição do Nome do Médico**: O nome do médico é exibido na primeira coluna da tabela.
2. **Excluir Médico**: Há um link para excluir o médico, que é confirmado pelo JavaScript antes de ser realizado.
3. **Editar Médico**: Há um link para editar os dados do médico, que redireciona para a página de edição.
4. **Incluir Novo Médico**: O link "Incluir novo médico" redireciona para a página onde é possível adicionar um novo médico ao sistema.
5. **Retornar ao Menu Principal**: O link "Retornar" redireciona para o menu administrativo principal.

## Código HTML

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Documento sem título</title>
</head>

<body>
<table width="578" height="220" border="1">
  <tr>
    <td width="418">Nome do médico</td>
    <td width="144" colspan="2" rowspan="3">
        <p><a href="form_inc_med.php">Incluir novo médico</a></p>
        <p><a href="menuadm.php">Retornar</a></p>
    </td>
  </tr>
  <tr>
    <td>
        <a href="exc_aluno.php?cod=<?php echo $linha[0];?>" onclick="javascript:return confirmaExclusaoRegistro();">Excluir</a>&nbsp;
    </td>
  </tr>
  <tr>
    <td>
        <a href="alt_med.php?cod=<?php echo $linha[0];?>">
            <img src="imagens/pencil.png" width="16" height="16" border="0"/>&nbsp;
        </a>
    </td>
  </tr>
</table>
</body>
</html>
````

