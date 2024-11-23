# Eco Track

### Link p/ apresentação da solução: https://www.youtube.com/watch?v=tvKSlDiB8sQ

### Link do video comprovando o funcionamento do App (DO ZERO): https://youtu.be/KkRSq7GKQMA

## Integrantes do Grupo

### Kauã Almeida Silveira - RM552618
### Rafael Vida - RM553721
### Gustavo Maia - RM553270

RESUMO 
Com base nos conhecimentos adquiridos em sala de aula, este projeto visa proporcionar a população uma maneira mais simples e automatizada de monitorar o uso energético de sua casa, obtendo relatórios do consumo de energia dos cadastros feitos pelos próprios usuários, através de um aplicativo. 
 
DESCRIÇÃO DO PROBLEMA A RESOLVER 
Muitas pessoas enfrentam dificuldades em gerenciar seu consumo de energia em casa. A complexidade de entender como cada eletrodoméstico impacta na conta de luz é um dos principais desafios. A falta de conhecimento sobre o tempo de uso e o consumo real de cada aparelho agrava essa situação, dificultando a tomada de decisões para economizar energia.  
Em resumo, a ausência de informações precisas sobre o consumo energético doméstico impede que as pessoas adotem medidas eficazes para reduzir seus gastos e contribuir para um futuro mais sustentável. 
 
OBJETIVOS DA SOLUÇÃO IDEALIZADA 
O aplicativo tem como objetivo principal facilitar a gestão do consumo de energia em casa. Ele permitirá que os usuários: 
Monitorem o consumo de cada eletrodoméstico: Através do cadastro dos aparelhos e do acompanhamento do tempo de uso, os usuários terão uma visão clara de onde está indo a energia consumida em casa. 
 
Acompanhem o consumo total da casa: O aplicativo gerará relatórios personalizados, oferecendo um panorama completo do consumo de energia da residência. 
 
Recebam dicas para economizar: O aplicativo fornecerá sugestões reduzir o consumo, como otimizar hábitos de consumo, ajustar configurações dos aparelhos e escolher modelos mais eficientes. 
 
CONCLUSÃO 
Ao democratizar o acesso a informações detalhadas sobre o consumo energético, o aplicativo contribui para a conscientização dos usuários a respeito de seus hábitos de consumo. Com a identificação de padrões de consumo, os usuários podem implementar medidas de eficiência energética de forma mais eficaz, impactando positivamente tanto seus bolsos quanto o meio ambiente. 

### ENTREGA DEVOPS INSTRUÇÕES

## AVISO IMPORTANTE - DEVOPS - ESTE PROJETO ESTÁ FUNCIONANDO PERFEITAMENTE NO AZURE
## E A API ESTÁ FUNCIONANDO E SE COMUNICANDO COM REQUISIÇÕES DE QUALQUER LUGAR
## O BANCO DE DADOS ORACLE ESTÁ HOSPEDADO EM UM SERVIDOR REMOTO DA FIAP
## TUDO ESTÁ FUNCIONANDO PERFEITAMENTE !!! 

- Construimos uma Dockerfile para a aplicação Spring Boot, e a aplicação foi dockerizada e publicada no Docker Hub.
- Na vm do Azure, foi logado no Docker Hub e a imagem foi baixada e rodada.
- Configuramos o Azure para liberar a porta 8080 para a aplicação Spring Boot.

## Como testar a aplicação

- O link para a aplicação rodando no Azure é: http://191.232.39.193:8080
- Para testar a aplicação, é necessário utilizar o Postman e importar a coleção de requisições.
- Exemplo de requisição: http://191.232.39.193/state
- Para testar a aplicação, é necessário realizar o login e obter o token JWT, e inseri-lo no Authorization das requisições, como bearer token.
- A aplicação está rodando no Azure, e o banco de dados Oracle está hospedado em um servidor remoto da FIAP.

![DESENHO-ARQUITETURA](./desenho.png)

FLUXO DE DADOS 

1. Usuário Interage com a VM: 
Entrada: O usuário realiza uma ação na máquina virtual (VM), como acessar um aplicativo, enviar uma requisição ou inserir dados de um formulário. 
Processamento: A VM recebe a solicitação do usuário e a encaminha para o próximo componente na cadeia, que é o orquestrador Docker. 

2. Docker: 
Função: O Docker gerencia o container do mesmo, distribuindo as tarefas entre ele. 
Processamento: Ao receber a solicitação da VM, o Docker direciona a requisição para o container da API Java. 

3. API Java: 
Função: A API Java realiza o processamento principal da aplicação. 
Processamento: A API Java processa a requisição recebida e manda para o banco de dados 

4. Banco de Dados FIAP: 
Função: O banco de dados armazena os dados da aplicação. 
Processamento: Ao receber uma requisição da API Java, o banco de dados realiza a operação solicitada (consulta, inserção, atualização ou exclusão) e retorna os resultados para a API Java. 
