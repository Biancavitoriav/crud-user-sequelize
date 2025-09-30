# Sistema de Gerenciamento de Usuários e Endereços com Node.js e Sequelize

Este projeto é uma aplicação web completa que utiliza **Node.js**, **Express**, **Sequelize** e **MySQL** para gerenciar usuários e seus atributos. Ele implementa um sistema CRUD com interface utilizando **Handlebars**.

---

## 📝 Funcionalidades

- **Gerenciamento de Usuários**
  - Criar, visualizar, atualizar e deletar usuários.
  - Campos principais: `nome`, `email`, `senha` (armazenada de forma segura), `telefone`, `data de nascimento`.

- **Gerenciamento de Endereços**
  - Associar múltiplos endereços a cada usuário.
  - Campos principais: `rua`, `número`, `bairro`, `cidade`, `estado`, `CEP`, `complemento`.

- **Relações**
  - Um **usuário** pode ter **múltiplos endereços** (`hasMany`).
  - Cada **endereço** pertence a um **usuário** (`belongsTo`).

- **Interface Web**
  - Páginas para visualização e manipulação dos registros de usuários e endereços.
  - Renderização dinâmica com **Handlebars**.

- **Integração com MySQL**
  - Banco de dados relacional para armazenar usuários e endereços.
  - Configuração via **Sequelize ORM**.

---

## 🛠️ Tecnologias Utilizadas

- **Node.js**: Ambiente de execução JavaScript.
- **Express**: Framework web para Node.js.
- **Sequelize**: ORM para interação com o banco de dados.
- **MySQL**: Banco de dados relacional.
- **Handlebars**: Template engine para renderização de páginas HTML.
- **Nodemon**: Reinicia automaticamente o servidor durante o desenvolvimento.

---

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter:

- **Node.js** (versão 14 ou superior) instalado.
- Editor de código (recomendado: **VSCode**).
- **Docker** instalado (Docker Desktop ou equivalente).
- **MySQL** (via container ou local).

---

## 🚀 Como Executar

### 1. Clone o Repositório

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

### 2. **Baixe as dependencias**

```bash
npm install -y
```

### 2. **Rode um container mysql (nesse exemplo, a senha é 1234, mas você coloca a que preferir)**

```bash
docker run -d --name mysql-container -e MYSQL_ROOT_PASSWORD=1234 -p 3306:3306 -v mysql_data:/var/lib/mysql mysql:latest
docker exec -it mysql-container mysql -uroot -p1234
```

### 4. **Crie o database dentro do banco rodando a query abaixo**

```bash
CREATE DATABASE nodesequelize CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
Query OK, 1 row affected (0.03 sec)

mysql> USE nodesequelize;
```

### 5. **No arquivo db/conn.js, certifique-se de que as configurações batem com a do seu banco**

```bash
  const sequelize = new Sequelize('nome do database', 'usuario', 'senha', {
  host: 'host',
  dialect: 'mysql',
```

### 6. **Rode a aplicação em desenvolvimento**

```bash
npm run dev
```
