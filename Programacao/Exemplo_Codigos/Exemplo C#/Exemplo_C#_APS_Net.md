# Exemplo C# | ASP NET | Tecnico OLD | Cadastro de Hospedagem

Esse código foi desenvolvido em um projeto de um sistema de hospedagem (talvez para gerenciar pacotes e tarifas de hospedagens). É uma página ASP.NET com um formulário simples para cadastrar informações como nome da hospedagem, tarifa e pacotes disponíveis. O código é antigo (2014), e não lembro os detalhes exatos de como tudo foi implementado. 

Aqui está um resumo do que está acontecendo na página.

### `Esse Codigo foi desevolvido no tecnico nem eu muito menos eu lembra KKKKK`


### Banco de dados Usado | `Suposição`:

````sql
-- Criação do Banco de Dados
CREATE DATABASE SistemaHospedagem;

USE SistemaHospedagem;

-- Tabela para armazenar Pacotes
CREATE TABLE PACOTES (
    id INT IDENTITY(1,1) PRIMARY KEY,   -- ID do pacote (chave primária)
    pacote NVARCHAR(100) NOT NULL        -- Nome do pacote (ex: "Pacote Básico", "Pacote Premium")
);

-- Inserir alguns pacotes para exemplificar
INSERT INTO PACOTES (pacote) VALUES
('Pacote Básico'),
('Pacote Premium'),
('Pacote Luxo');

-- Tabela para armazenar as Hospedagens
CREATE TABLE HOSPEDAGEM (
    id INT IDENTITY(1,1) PRIMARY KEY,    -- ID da hospedagem (chave primária)
    NomeHospedagem NVARCHAR(100) NOT NULL,  -- Nome da hospedagem
    ValorTarifa DECIMAL(10, 2) NOT NULL,   -- Valor da tarifa (por exemplo, 100.00)
    PacoteId INT,                          -- ID do pacote associado (chave estrangeira)
    CONSTRAINT FK_Pacote FOREIGN KEY (PacoteId) REFERENCES PACOTES(id)  -- Relacionamento com PACOTES
);

-- Exemplo de inserção de hospedagens
INSERT INTO HOSPEDAGEM (NomeHospedagem, ValorTarifa, PacoteId) VALUES
('Hotel Praia Azul', 150.00, 2), -- Pacote Premium
('Pousada das Montanhas', 80.00, 1), -- Pacote Básico
('Resort Bela Vista', 250.00, 3); -- Pacote Luxo
````
---

````html
<%@ Page Title="" Language="C#" MasterPageFile="~/MasterPage.master" AutoEventWireup="true" CodeFile="ADDHOSPEDAGEM.ASPX.cs" Inherits="ADDHOSPEDAGEM" %>

<asp:Content ID="Content1" ContentPlaceHolderID="head" Runat="Server">
</asp:Content>

<asp:Content ID="Content2" ContentPlaceHolderID="ContentPlaceHolder1" Runat="Server">
    <table cellpadding="0" cellspacing="0" class="auto-style1">
        <!-- Campo Pacotes -->
        <tr>
            <td>Pacotes:
                <asp:DropDownList ID="DropDownList1" runat="server" DataSourceID="SqlDataSourcepacotes" DataTextField="pacote" DataValueField="id">
                </asp:DropDownList>
                <asp:SqlDataSource ID="SqlDataSourcepacotes" runat="server" ConnectionString="<%$ ConnectionStrings:ConnectionString %>" ProviderName="<%$ ConnectionStrings:ConnectionString.ProviderName %>" SelectCommand="SELECT * FROM [PACOTES]"></asp:SqlDataSource>
            </td>
        </tr>
        <!-- Campo Nome da Hospedagem -->
        <tr>
            <td>Nome da hospedagem:
                <asp:TextBox ID="TextBox1" runat="server" MaxLength="10"></asp:TextBox>
            </td>
        </tr>
        <!-- Campo Valor da Tarifa -->
        <tr>
            <td>Valor da Tarifa:
                <asp:TextBox ID="TextBox2" runat="server"></asp:TextBox>
            </td>
        </tr>
        <tr>
            <td>&nbsp;</td>
        </tr>
        <tr>
            <td>
                <asp:Button ID="Button1" runat="server" Text="Gravar" />
                <asp:Button ID="Button2" runat="server" Text="Cancelar" />
            </td>
        </tr>
    </table>
</asp:Content>
````

### Master Page

````html
<%@ Master Language="C#" AutoEventWireup="true" CodeFile="MasterPage.master.cs" Inherits="MasterPage" %>

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title>Master Page - Sistema de Hospedagem</title>
    <asp:ContentPlaceHolder id="head" runat="server"></asp:ContentPlaceHolder>
    <style type="text/css">
        .auto-style1 {
            width: 100%;
        }
        .auto-style2 {
            width: 457px;
        }
        .auto-style3 {
            width: 132px;
            height: 101px;
        }
    </style>
</head>
<body>
    <form id="form1" runat="server">
        <table class="auto-style1">
            <tr>
                <td class="auto-style2">
                    <!-- Menu de navegação -->
                    <asp:TreeView ID="TreeView1" runat="server" DataSourceID="SiteMapDataSource1" ShowLines="True"></asp:TreeView>
                    <asp:SiteMapDataSource ID="SiteMapDataSource1" runat="server" />
                </td>
                <td>
                    <img alt="" class="auto-style3" src="imagens/icone_compania.jpg" />
                </td>
            </tr>
            <tr>
                <td colspan="2">
                    <asp:ContentPlaceHolder id="ContentPlaceHolder1" runat="server"></asp:ContentPlaceHolder>
                </td>
            </tr>
            <tr>
                <td colspan="2">&nbsp;</td>
            </tr>
            <tr>
                <td colspan="2
````

### `ADDHOSPEDAGEM.ASPX.cs`

- Agora, a parte que faz o processamento no back-end, como gravar os dados no banco de dados e lidar com o botão "Gravar" e "Cancelar". Vamos supor que você está usando SQL Server e já tem uma tabela

````c#
using System;
using System.Data.SqlClient;

public partial class ADDHOSPEDAGEM : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        // Lógica de carregamento, caso precise
    }

    // Método para gravar os dados no banco de dados
    protected void Button1_Click(object sender, EventArgs e)
    {
        string nomeHospedagem = TextBox1.Text;
        string valorTarifa = TextBox2.Text;
        string pacoteId = DropDownList1.SelectedValue;  // Pega o id do pacote selecionado

        // Conexão com o banco de dados
        string connectionString = System.Configuration.ConfigurationManager.ConnectionStrings["ConnectionString"].ConnectionString;
        using (SqlConnection conn = new SqlConnection(connectionString))
        {
            string query = "INSERT INTO HOSPEDAGEM (NomeHospedagem, ValorTarifa, PacoteId) VALUES (@NomeHospedagem, @ValorTarifa, @PacoteId)";
            SqlCommand cmd = new SqlCommand(query, conn);

            // Parâmetros para evitar SQL Injection
            cmd.Parameters.AddWithValue("@NomeHospedagem", nomeHospedagem);
            cmd.Parameters.AddWithValue("@ValorTarifa", valorTarifa);
            cmd.Parameters.AddWithValue("@PacoteId", pacoteId);

            conn.Open();
            cmd.ExecuteNonQuery();  // Executa o comando no banco de dados
            conn.Close();
        }

        // Talvez uma mensagem de sucesso ou redirecionamento
        Response.Write("<script>alert('Hospedagem cadastrada com sucesso!');</script>");
    }

    // Método para cancelar o cadastro (pode redirecionar ou limpar os campos)
    protected void Button2_Click(object sender, EventArgs e)
    {
        // Limpar os campos de entrada
        TextBox1.Text = "";
        TextBox2.Text = "";
        DropDownList1.SelectedIndex = -1;  // Desmarcar a seleção do DropDownList
    }
}
````

### `Conexção de Banco de dados`

````xml
<connectionStrings>
    <add name="ConnectionString" 
         connectionString="Server=localhost; Database=SeuBancoDeDados; Integrated Security=True;" 
         providerName="System.Data.SqlClient" />
</connectionStrings>
````




