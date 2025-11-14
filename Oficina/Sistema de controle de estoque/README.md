# 📦 Sistema de Controle de Estoque

Aplicação desktop desenvolvida em **Java (Maven)** para gestão de
entradas, saídas, usuários e estoque geral.\
O sistema utiliza **MySQL** via **Docker Desktop**, garantindo que
qualquer usuário possa rodá-lo facilmente em sua máquina.

------------------------------------------------------------------------

## 🧾 Descrição do Projeto: Sistema de Controle de Estoque para Oficina

Durante um projeto extensivo na faculdade **Estácio**, participei de uma
iniciativa colaborativa para desenvolver um sistema de controle de
estoque específico para uma **oficina mecânica**.

O principal objetivo deste sistema é:

-   Gerenciar o inventário de peças e produtos.\
-   Evitar falta de estoque.\
-   Controlar entradas e saídas com precisão.\
-   Facilitar o acesso às informações por meio de uma interface simples
    e intuitiva.


![Sistema de Controle de
Estoque](https://github.com/renangfs/Oficina2DB/assets/61218420/5ac2fa59-d1da-4692-b787-55d6859e63f3)

------------------------------------------------------------------------

## 🚀 Tecnologias Utilizadas

-   **Java 17+**
-   **Maven**
-   **Docker Desktop**
-   **MySQL (container Docker)**
-   **MySQL Workbench**
-   **Swing (UI)**
-   **JDBC**

------------------------------------------------------------------------

# 🐳 1. Como rodar com Docker (Banco de Dados)

### ✔️ Pré-requisitos

-   Docker Desktop\
-   MySQL Workbench\
-   Java 17+\
-   IDE (IntelliJ / Eclipse / NetBeans)

------------------------------------------------------------------------

# 🗄️ 2. Criar o container MySQL no Docker

Execute no terminal:

    docker pull mysql:8
    docker run --name estoque-mysql -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_DATABASE=oficinaV2 -p 3306:3306 -d mysql:8

Isso criará:

-   Banco: **oficinaV2**
-   Usuário: **root**
-   Senha: **123456**

------------------------------------------------------------------------

# 🛠️ 3. Importar o banco no MySQL Workbench

1.  Abra o **Workbench**\
2.  Crie uma conexão:
    -   **Host:** localhost\
    -   **User:** root\
    -   **Password:** 123456\
3.  Vá em:\
    **Server \> Data Import \> Import from Self-Contained File**\
4.  Selecione: `oficinaV2.sql`\
5.  Importe o banco.

------------------------------------------------------------------------

# 🧩 4. Configurar o ConnectionFactory.java

No caminho:

    src/main/java/org/example/ConnectionFactory.java

Configure assim:

``` java
String url = "jdbc:mysql://localhost:3306/oficinaV2";
String user = "root";
String password = "123456";
```

------------------------------------------------------------------------

# ▶️ 5. Como rodar o sistema

Abra na IDE o arquivo:

    src/main/java/org/example/Main.java

Clique em **Run**.

A interface Swing será iniciada automaticamente.

------------------------------------------------------------------------

# 📁 Estrutura do Projeto

    Sistema-de-controle-de-estoque/
     └── Oficina/
         └── Sistema de controle de estoque/
             ├── src/main/java/org/example/
             │   ├── Main.java
             │   ├── Login.java
             │   ├── Cadastro.java
             │   ├── Entrada.java
             │   ├── Saida.java
             │   ├── Estoque.java
             │   ├── ConnectionFactory.java
             │   └── ...
             ├── oficinaV2.sql
             ├── pom.xml
             └── out/artifacts/

------------------------------------------------------------------------

# ❗ Problemas Comuns

### ❌ *"Communications link failure"*

O container MySQL pode estar desligado.

✔ Execute:

    docker start estoque-mysql

------------------------------------------------------------------------

### ❌ *"Access denied for user 'root'"*

A senha usada no código está diferente da senha do container.

✔ Ajuste no `ConnectionFactory.java`.

------------------------------------------------------------------------

### ❌ Dependências não carregam no Maven

Execute:

    mvn clean install

------------------------------------------------------------------------

# 📜 Licença

Este projeto é livre para uso educacional.

------------------------------------------------------------------------

# 🤝 Contribuições

Contribuições são bem-vindas!\
Crie issues, envie sugestões ou abra pull requests.

------------------------------------------------------------------------

## 🧑‍💻 Autor

**Rodrigo Ferreira da Silva Filho**  
✉️ [contato.rodrigo.tech@gmail.com]<br>
🔗 [https://www.linkedin.com/in/rodrigo-ferreira-325527272/]<br>
