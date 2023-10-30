# Cronômetro com Lap, Parar e Voltas em Java e MySQL

Este é um projeto de cronômetro em Java que permite marcar o tempo de duas voltas em um circuito e enviar os dados para um banco de dados MySQL. Abaixo, documentaremos o código em Markdown para incluí-lo em seu arquivo README no GitHub.

## Descrição do Projeto

O projeto consiste em um aplicativo de cronômetro com as seguintes funcionalidades:

- Iniciar o cronômetro.
- Parar o cronômetro.
- Marcar voltas durante a corrida.
- Armazenar o tempo das duas primeiras voltas em um banco de dados MySQL.

## Dependências

Para executar este projeto, você precisará das seguintes dependências:

- Java Development Kit (JDK)
- MySQL Server
- Biblioteca JDBC para MySQL (normalmente incluída nas bibliotecas padrão do JDK)

## Configuração do Banco de Dados

Antes de executar o projeto, você deve configurar o banco de dados MySQL:

1. Crie um banco de dados chamado "cronometro_teste".
2. Defina seu nome de usuário e senha do MySQL no código onde está escrito `root` e `senha`.

## Execução do Projeto

Para executar o projeto, compile e execute a classe `CronometroComLapPararVoltas` no seu ambiente de desenvolvimento Java.

## Funcionalidades

- Pressione o botão "Iniciar" para iniciar o cronômetro.
- Pressione o botão "Parar" para parar o cronômetro.
- Pressione o botão "Volta" para marcar uma volta.
- Após a segunda volta, os tempos das duas voltas serão armazenados no banco de dados MySQL.

## Observações

- O projeto utiliza a biblioteca Swing para a interface gráfica.
- O código assume que o banco de dados MySQL está em execução na porta padrão (3306).

## Exemplo de Conexão ao Banco de Dados

```java
try {
    Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/cronometro_teste", "root", "senha");

    // Insere as variáveis tempoVolta1 e tempoVolta2 na tabela 
    String query = "INSERT INTO voltas (volta1, volta2) VALUES (?, ?)";
    PreparedStatement statement = conn.prepareStatement(query);
    statement.setString(1, tempoVolta1);
    statement.setString(2, tempoVolta2);
    statement.executeUpdate();

    // Feche a conexão com o banco de dados
    conn.close();
} catch (SQLException ex) {
    ex.printStackTrace();
}
```
## Contribuição

Sinta-se à vontade para contribuir com melhorias, correções de bugs ou novos recursos para este projeto. Basta criar um fork do repositório, fazer as alterações desejadas e enviar um pull request.

## Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE) para obter mais informações.

---

Espero que essa documentação seja útil para você compartilhar seu projeto no GitHub. Certifique-se de atualizar os detalhes específicos do seu projeto, como o nome do autor e outras informações relevantes.
