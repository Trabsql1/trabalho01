# TRABALHO 01:  Título do Trabalho
Trabalho desenvolvido durante a disciplina de Banco de Dados do Integrado

# Sumário

### 1. COMPONENTES<br>
Integrantes do grupo<br>
Weverton Gomes: wevertoncapixaba22@gmail.com<br>
Mateus Maioli: matgiacomin@gmail.com.com<br>
...

### 2.INTRODUÇÃO E MOTIVAÇAO<br>
Este documento contém a especificação do projeto do banco de dados do projeto Whitrash 
<br>e motivação da escolha realizada. <br>

>A Wite tem como meta tornar a sociedade mais limpa e ajudar o meio ambiente, além de tornar o dia-a-dia dos cidadãos mais prático e simples. Considerando que os problemas ambientais que nós, como uma sociedade, enfrentamos no presente e com o objetivo de fazer o máximo para evitar o agravamento de tais problemas e agregar ao meio social. Nosso sistema consiste em um banco de dados construído através da coleta de dados fornecidos por cada indivíduo representante de uma residência, sendo os mais importantes endereço, quantidade de dependentes, quantidade de cada tipo de dejeto, informações pessoais do representante e o agendamento para a passagem do coletor.  O sistema gerenciará a coleta do material contido nos containers especialmente fornecidos pela Whitrash por meio de coletores automáticos e independentes.
 

### 3.MINI-MUNDO Novo<br>

> Nosso sistema conterá as informações descritas a seguir. A respeito da residência serão armazenados, nome da rua, número da casa, número do quarteirão de acordo com uma divisão realizada pela direção do condimínio de cada localidade e enviada para nossa empresa, quantidade de dependentes. A respeito do representante serão armazenados nome completo, cpf ,rg, cópia escaneada de um comprovante de residência,(orgânico, reciclável, pilhas e bateria, e médicos). O agendamento deve ser feito a cada visita, ou por um determinado tempo, mas também será armazenado.
Cada coletor pode ser direcionado a mais de um quarteirão após o término de seu quarteirão padrão, e caso um não termine sua coleta ele pode retornar ou outro coletor disponível será enviado. Após terminarem sua rota designada ou atingirem capacidade máxima os coletores se dirigirão para o centro de eliminação, ondde cada um dos dependentes do representante será requisitada para determinação do tipo de coletor. Após terminarem sua e os dejetos terão suas respectivas rotas. Lixo comum será descartado de forma sustentável, lixo reciclável será reciclado e lixo orgânico será enviado ao centro de compostagem e transformado em fertilizante orgânico.  Todos os dados podem ser alterados caso o usuário requisite e é imprescindível a atualização dos dados de forma correta para evitar problemas.


### 4.RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>

![Alt text](https://user-images.githubusercontent.com/51093933/58552933-ff2ccd00-81e9-11e9-8677-82a3865de28e.png?raw=true "Title")
![Pdf para o projeto Witrash da empresa Wite](https://github.com/discipint/trabalho01/files/3232159/New.Project.pdf?raw=true "Empresa Devcom")

#### 4.1 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO?
   Nossa empresa, a Wite, possui em seu projeto de coleta de lixo, o Witrash, diversos relatórios. Os principais podem ser vistos a seguir:

    • Um relatório que informa os dados de cada usuário, como  nome, endereço, sexo,  RG, CPF e título de eleitor, tal como os nomes e os sexos de seus dependentes além de seu parentesco  com o usúario.
    • Um relatório que contém as principais informações dos coletores, sendo elas  o código de todos os coletores, o tipo de lixo que eles podem carregar, sua capacidade máxima, e quanto dessa capacidade já foi preenchida.
    • Um relatório que possui as informações sobre a atual situação dos coletores, como os dados de localização de todos os coletores, mostrados em um mapa interativo e em tempo real, os horários que eles irão passar em cada ponto, e os agendamentos feitos por usuários.
    • Um relatório contendo o progresso de coleta diária, mostrando o total de quarteirões,  quais desses quarteirões já foram finalizados, o progresso nos que não foram e os coletores enviados para cada um deles.
    • Um relatório que verifica que tipo de material entra em que tipo de coleta, entre orgânico, reciclável, hospitalar, e radioativo.

 #### 4.2 TABELA DE DADOS DO SISTEMA:
 Tabela com os principais dados do projeto Witrash:  
![Tabela de dados da Wite](https://github.com/Trabsql1/trabalho01/blob/master/Weverton_e_Mateus.ods?raw=true "Tabela - Wite")

### 5.MODELO CONCEITUAL<br>          
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/Conc.png?raw=true "Modelo Conceitual")      
    
#### 5.1 Validação do Modelo Conceitual
    [Beatriz e Júlia: [Beatriz]
    [Caio Lessa e Lucas]: [Caio L]
    
#### 5.2 DESCRIÇÃO DOS DADOS 
      Representante: uma tabela que contem informações relativas ao usuário denominado represente.
         Tag: Uma chave de um chip RFID que libera a abertura da lixeira ao representante. Ele também é identificado por essa tag
         Nome: Campo que armazena o nome do representante.
         RG: Campo que armazena o RG do representante.
         CPF: Campo que armazena o CPF do representante.
      Dependente: Tabela que armazena dados dos dependentes atrelados ao representante.
         Nome: Campo que armazena o nome do dependente.
         Código: Número unico do dependente de acordo com a quantidade de dependentes atreladas ao representante. Utilizado como chave.
         Relação: Campo que armazena a relação entre o dependente e o representante.
         Idade: Campo que armazena a idade do dependente.
         Gênero: Campo que armazena o gênero do dependente.
      Residência: Tabela que armazena informações da residência representada.
         Casa: Campo que armazena o número da residência. Utilizado como chave.
         Rua: Campo que armazena o nome da rua que a residência se encontra.
      Lixeira: Tabela que armeza as informações de cada lixeira
         Serial: Código único que cada lixeira possui
         Tipo: Armazena o tipo de lixo que cada lixeira carrega
         Peso: Armazena o peso atual da lixeira
     A
         ## Marco de Entrega 06 em: (22/05/2019)<br>

### 6	MODELO LÓGICO<br>
        a) inclusão do modelo lógico do banco de dados
        b) verificação de correspondencia com o modelo conceitual 
        (não serão aceitos modelos que não estejam em conformidade)

### 7	MODELO FÍSICO<br>
        a) inclusão das instruções de criacão das estruturas DDL 
        (criação de tabelas, alterações, etc..)          

## Marco de Entrega 07 em: (27/05/2019)<br>

### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
        a) inclusão das instruções de inserção dos dados nas tabelas criadas pelo script de modelo físic
        b) formato .SQL

#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELA E INSERÇÃO DOS DADOS
        a) Junção dos scripts anteriores em um único script 
        (create para tabelas e estruturas de dados + dados a serem inseridos)
        b) Criar um novo banco de dados para testar a restauracao 
        (em caso de falha na restauração o grupo não pontuará neste quesito)
        c) formato .SQL
#### 8.3 INCLUSÃO DO SCRIPT PARA EXCLUSÃO DE TABELAS EXISTENTES, CRIAÇÃO DE TABELA NOVAS E INSERÇÃO DOS DADOS
        a) Junção dos scripts anteriores em um único script 
        (Drop table + Create de tabelas e estruturas de dados + dados a serem inseridos)
        b) Criar um novo banco de dados para testar a restauracao 
        (em caso de falha na restauração o grupo não pontuará neste quesito)
        c) formato .SQL

## Marco de Entrega 08 em: (29/05/2019)<br>

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + imagens (print da tela) mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>
#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>
#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    b) Criar no mínimo 3 consultas com operadores aritméticos 
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas
#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.


    
#### 9.5	ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>


#### 9.6	CONSULTAS COM JUNÇÃO E ORDENAÇÃO (Mínimo 6)<br>
        a) Uma junção que envolva todas as tabelas possuindo no mínimo 3 registros no resultado
        b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho
        

### ATUALIZAÇÃO DA DOCUMENTAÇÃO DOS SLIDES PARA APRESENTAÇAO SEMESTRAL (Mínimo 6 e Máximo 10)<br>


#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>

#### 9.8	CONSULTAS COM LEFT E RIGHT JOIN (Mínimo 4)<br>
#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
        a) Uma junção que envolva Self Join
        b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho
#### 9.10	SUBCONSULTAS (Mínimo 3)<br>

#### 9.11	LISTA DE CODIGOS DAS FUNÇÕES E TRIGGERS<br>
        Detalhamento sobre funcionalidade de cada código.
        a) Objetivo
        b) Código do objeto (função/trigger)
        c) exemplo de dados para aplicação
        d) resultados em forma de tabela/imagem
<br>


#### 9.12	GERACAO DE DADOS (MÍNIMO DE 100 MIL REGISTROS PARA PRINCIPAL RELAÇAO)<br>
        a) principal tabela do sistema deve ter no mínimo 100 mil registros
        b) tabelas diretamente relacionadas a tabela principal 10 mil registros
        c) tabelas auxiliares de relacao multivalorada mínimo de 10 registros
        d) registrar o tempo de inserção em cada uma das tabelas do banco de dados
        e) especificar a quantidade de registros inseridos em cada tabela
        Para melhor compreensão verifiquem o exemplo na base de testes:<br>
        https://github.com/discipbd2/base-de-testes-locadora
        

#### 9.13	Backup do Banco de Dados<br>
        Detalhamento do backup.
        a) Tempo
        b) Tamanho
        c) Teste de restauração (backup)
        d) Tempo para restauração
        e) Teste de restauração (script sql)
        f) Tempo para restauração (script sql)
<br>

Data de Entrega: (Data a ser definida)
<br>

#### 9.14	APLICAÇAO DE ÍNDICES E TESTES DE PERFORMANCE<br>
    a) Lista de índices, tipos de índices com explicação de porque foram implementados nas consultas 
    b) Performance esperada VS Resultados obtidos
    c) Tabela de resultados comparando velocidades antes e depois da aplicação dos índices (constando velocidade esperada com planejamento, sem indice e com índice Vs velocidade de execucao real com índice e sem índice).
    d) Escolher as consultas mais complexas para serem analisadas (consultas com menos de 2 joins não serão aceitas)
    e) As imagens do Explain devem ser inclusas no trabalho, bem como explicações sobre os resultados obtidos.
    f) Inclusão de tabela mostrando as 10 execuções, excluindo-se o maior e menor tempos para cada consulta e 
    obtendo-se a media dos outros valores como resultado médio final.
<br>
    Data de Entrega: (Data a ser definida)
<br>   

### 10	ATUALIZAÇÃO DA DOCUMENTAÇÃO DOS SLIDES PARA APRESENTAÇAO FINAL (Mínimo 6 e Máximo 10)<br>
<br>
    Data de Entrega: (Data a ser definida)
<br>

### 11 Backup completo do banco de dados postgres 
    a) deve ser realizado no formato "backup" 
        (Em Dump Options #1 Habilitar opções Don't Save Owner e Privilege)
    b) antes de postar o arquivo no git o mesmo deve ser testado/restaurado por outro grupo de alunos/dupla
    c) informar aqui o grupo de alunos/dupla que realizou o teste.

    
### 12	TUTORIAL COMPLETO DE PASSOS PARA RESTAURACAO DO BANCO E EXECUCAO DE PROCEDIMENTOS ENVOLVIDOS NO TRABALHO PARA OBTENÇÃO DOS RESULTADOS<br>
        a) Outros grupos deverão ser capazes de restaurar o banco 
        b) executar todas as consultas presentes no trabalho
        c) executar códigos que tenham sido construídos para o trabalho 
        d) realizar qualquer procedimento executado pelo grupo que desenvolveu o trabalho

### 13	DIFICULDADES ENCONTRADAS PELO GRUPO<br>  

    
Data de Entrega final: (Data a ser definida)
<br>

       
### 14  FORMATACAO NO GIT: https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
   
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/

#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/

### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. Caso existam arquivos com conteúdos sigilosos, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário deste GIT, para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.


Link para BrModelo:<br>
http://sis4.com/brModelo/brModelo/download.html
<br>


Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")


        
        


    





