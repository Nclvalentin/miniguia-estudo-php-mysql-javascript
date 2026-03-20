# 💻 Miniguia de Estudos: PHP + MySQL + JavaScript

## 📌 Contexto

Este projeto foi desenvolvido com o objetivo de criar um material de apoio utilizando o NotebookLM para estudo de desenvolvimento web com PHP, MySQL e JavaScript.

A proposta é centralizar conhecimento técnico e facilitar consultas durante a criação de projetos reais.

---

## 🎯 Objetivos

* Criar base para desenvolvimento de sistemas web
* Aprender a estruturar operações CRUD
* Implementar autenticação de usuários
* Melhorar o uso de IA com engenharia de prompts

---

## 📚 Curadoria de Fontes

* Apostila PHP básico
  http://www.etelg.com.br/paginaete/downloads/informatica/apostila_php.pdf

* Documentação MySQL
  https://downloads.mysql.com/docs/refman-8.4-en.pdf

* Tutorial CRUD
  https://www.tutorialrepublic.com/php-tutorial/php-mysql-crud-application.php

* Sistema de Login
  http://www.phptutorial.net/php-tutorial/php-login/

* Apostila JavaScript
  http://www.gurukultti.org/admin/notice/javascript.pdf

* Vídeo (Fetch API)
  http://www.youtube.com/watch?v=37vxWr0WgQk

---

## 🤖 Engenharia de Prompts

---

### 🔹 Prompt 1 — Conexão PHP + MySQL

**Prompt:**

> De forma resumida, explique como conectar PHP ao MySQL

**Resumo do aprendizado:**

* Existem 3 formas principais (MySQLi procedural, OO e PDO)
* PDO é mais seguro
* Ideal usar arquivo de configuração

**Resposta completa:**

```
Para conectar o PHP ao MySQL, você deve primeiro definir as credenciais de acesso, que incluem o servidor (host), o nome de usuário, a senha e o nome do banco de dados.

Existem três métodos principais para estabelecer essa comunicação:

1. MySQLi Procedural: Utiliza a função mysqli_connect() para criar a conexão e verifica se houve falha comparando o resultado a false.

2. MySQLi Orientado a Objetos: Cria-se uma nova instância da classe new mysqli(), tratando erros através da propriedade connect_error do objeto.

3. PDO (PHP Data Objects): Utiliza a classe new PDO() dentro de um bloco try...catch para capturar exceções caso a conexão falhe, sendo uma interface que suporta diversos bancos de dados.

Como boa prática, recomenda-se criar um arquivo de configuração centralizado, como o config.php, e utilizá-lo em outras páginas através da função require_once().

Além disso, é importante substituir as credenciais padrão por configurações reais do servidor antes de colocar o código em produção.

Por fim, as conexões devem ser encerradas após o uso utilizando funções como mysqli_close(), o método $mysqli->close() ou limpando a variável com unset($pdo).
```

---

### 🔹 Prompt 2 — CRUD estruturado

**Prompt:**

> Crie um CRUD estruturado com separação de arquivos em PHP

**Resumo do aprendizado:**

* Separação em arquivos melhora organização
* Uso de PDO + prepared statements
* Estrutura padrão de CRUD

**Resposta completa:**

```
Abaixo está a estrutura baseada nos tutoriais fornecidos:

1. Criando a Tabela no Banco de Dados

CREATE TABLE employees (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    address VARCHAR(255) NOT NULL,
    salary INT(10) NOT NULL
);

2. Arquivo de Configuração (config.php)

<?php
define('DB_SERVER', 'localhost');
define('DB_USERNAME', 'root');
define('DB_PASSWORD', '');
define('DB_NAME', 'demo');

try{
    $pdo = new PDO("mysql:host=" . DB_SERVER . ";dbname=" . DB_NAME, DB_USERNAME, DB_PASSWORD);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch(PDOException $e){
    die("ERRO: Não foi possível conectar. " . $e->getMessage());
}
?>

3. Página Principal (index.php)
Executa SELECT e exibe dados em tabela HTML.

4. create.php
Formulário + validação + INSERT com prepared statements.

5. read.php
Busca dados por ID.

6. update.php
Atualiza registros existentes.

7. delete.php
Remove registros com confirmação.

8. error.php
Tratamento de erro.

Dica: usar require_once para reutilizar conexão.
```

---

### 🔹 Prompt 3 — Integração JS + PHP

**Prompt:**

> Como integrar JavaScript com PHP

**Resumo do aprendizado:**

* Comunicação via Fetch API
* Uso de JSON
* Atualização dinâmica da interface

**Resposta completa:**

```
A integração entre JavaScript e PHP baseia-se na comunicação entre o lado do cliente (frontend) e o lado do servidor (backend).

Enquanto o PHP processa lógica de negócios e acessa o banco de dados no servidor, o JavaScript lida com a interatividade no navegador.

Principais formas:

1. Fetch API (AJAX)
JavaScript envia requisições HTTP para arquivos PHP sem recarregar a página.

2. PHP gerando JavaScript
PHP pode inserir valores dinâmicos no código JS.

3. Formulários
JS valida e envia dados para PHP.

Fluxo:
1. JS envia requisição
2. PHP processa
3. MySQL responde
4. JS atualiza a interface
```

---

### 🔹 Prompt 4 — Segurança (SQL Injection)

**Prompt:**

> De forma resumida, como usar Prepared Statements para evitar SQL Injection?

**Resumo do aprendizado:**

* Separar dados da query
* Uso obrigatório em sistemas reais
* Proteção contra ataques

**Resposta completa:**

```
O uso de Prepared Statements separa a lógica SQL dos dados enviados pelo usuário.

O PHP conecta ao MySQL usando PDO ou MySQLi.

CRUD representa Create, Read, Update e Delete.

JavaScript usa Fetch API para comunicação com PHP.

JSON é utilizado como formato de troca de dados.

Essa abordagem evita SQL Injection e aumenta a segurança do sistema.
```

---

## 🚀 Aplicação Prática

Este material será utilizado como base para desenvolvimento de sistemas reais, incluindo projetos de controle de dados e autenticação de usuários.

---


