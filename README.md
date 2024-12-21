# Exemplo de Conexão com Banco de Dados JDBC

## Descrição
Este projeto demonstra como estabelecer uma conexão com um banco de dados MySQL usando JDBC (Java Database Connectivity)
em uma aplicação Java simples. O código é estruturado de forma a facilitar a compreensão e o uso do JDBC, incluindo tratamento
de erros e carregamento de configurações a partir de um arquivo de propriedades.

## Estrutura do Projeto

`src/
├── application/
│   └── Program.java     # Classe principal da aplicação
└── db/
├── DB.java              # Classe responsável pela conexão com o banco de dados
└── DbException.java     # Classe de exceção personalizada`

## Pré-requisitos

- Java Development Kit (JDK) 8 ou superior.
- MySQL Server instalado e em execução.
- Dependência do MySQL Connector/J no projeto (se estiver usando Maven, conforme indicado abaixo).

## Configuração

1. **Banco de Dados**: Certifique-se de que o servidor MySQL esteja em execução e que o banco de dados `coursejdbc` exista. 
Você pode criar o banco de dados usando o seguinte comando SQL:

    ```sql
    CREATE DATABASE coursejdbc;
    ```

2. **Arquivo de Propriedades**: Crie um arquivo chamado db.properties na raiz do seu diretório do projeto com o seguinte conteúdo:

`user=root
password=123456
dburl=jdbc:mysql://localhost:3306/coursejdbc
useSSL=false`

**Obs.**: Substitua os valores de `user` e `password` pelas credenciais do seu banco de dados, se necessário.

3. Dependências: Se você estiver usando Maven, adicione a seguinte dependência ao seu arquivo `pom.xml`:

    ```xml
    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>8.0.23</version> <!-- Verifique se há uma versão mais recente -->
    </dependency>
    ```

## Como Executar
1. Compile o projeto. Se estiver usando um IDE como IntelliJ IDEA ou Eclipse, você pode usar o recurso de compilação integrado.

2. Execute a classe `Program.java`:
    
    ```bash
    java application.Program
    ```
   
3. O programa tentará estabelecer uma conexão com o banco de dados e, em seguida, fechará a conexão.

## Estrutura do Código
- **DbException.java**: Classe de exceção personalizada que estende `RuntimeException` para lidar com erros relacionados ao banco de dados.
- **DB.java**: Classe que contém métodos para obter e fechar a conexão com o banco de dados.
Ela carrega as propriedades de configuração a partir do arquivo `db.properties`.
- **Program.java**: Classe principal que contém o método `main`, onde a conexão com o banco de dados é estabelecida e fechada.

## Considerações Finais
Este exemplo fornece uma estrutura básica para conectar-se a um banco de dados MySQL usando JDBC em Java.
Ele pode ser expandido para incluir operações de banco de dados mais complexas, como consultas, inserções e atualizações.