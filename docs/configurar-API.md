## Como rodar a API localmente

Siga os passos abaixo para configurar o ambiente e iniciar a API:

1. Com o projeto clonado localmente, abra-o no IntelliJ.

2. Configure o ambiente no IntelliJ.
    - Acesse o menu _Project Structure_ (`Ctrl+Alt+Shift+S`).
    - Na aba _Project_, localize o campo _SDK_ e selecione o diretório da JDK configurado no seu sistema.

4. Instale as dependências do projeto com Maven
    - No terminal ou na aba _Maven_, execute o comando:
      ```bash
      mvn clean install
      ```  
      Esse comando irá baixar e instalar todas as informações necessárias para o projeto.

5. Suba a API com Spring Boot
    - Após a finalização do comando anterior, execute o seguinte comando para subir a API:
      ```bash
      mvn spring-boot:run
      ```  
    - A API será iniciada e estará disponível localmente na porta indicada no terminal de execução.

Feito! Sua API já está pronta para ser utilizada :)
