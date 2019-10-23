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

> Nosso sistema conterá as informações descritas a seguir. A respeito da residência serão armazenados, nome do local, tipo de local, número da casa e um código único da casa. A respeito dos dependentes temos a quantidade destes, sua relação com o representante, seu gênero, sua data de nascimento e seu nome. A respeito do representante serão armazenados nome completo, cpf ,rg, data de nascimento, genêro, número da casa onde mora e uma tag única para cada representante que confere a ele e seus dependentes acesso às lixeiras. A respeito das lixeiras serão armazenadas o tipo de lixo que ela pode armazenar, um código único de cada lixeira, o local em que ela se encontra, o capacidade total da lixeira, e o peso atual, que é verificado junto com quem jogou o lixo em qual momento. A respeito do local temos seu nome, sua latitude e sua longitude. A respeito dos coletores um código, do coletor, sua latitude e longitude, o peso total e o peso atual que, é claro, diz quanto de lixo o coletor já possui em seu interior. Após atingirem capacidade máxima os coletores se dirigirão para o centro de eliminação. Lixo reciclável será reciclado e lixo orgânico será enviado ao centro de compostagem e transformado em fertilizante orgânico, pílhas e baterias serão descartadas no centro de coleta,e lixo hospitalar será incinerado.   Todos os dados podem ser alterados caso o usuário requisite e é imprescindível a atualização dos dados de forma correta para evitar problemas.


### 4.RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>

![Alt text](IMG-20191002-WA0019.png?raw=true "Title")
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
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/conceitinho.png?raw=true "Modelo Conceitual")      
    
#### 5.1 Validação do Modelo Conceitual
    [Beatriz e Júlia: [Beatriz]
    [Caio Lessa e Lucas]: [Caio L]
    
#### 5.2 DESCRIÇÃO DOS DADOS 
      Usuário: uma tabela que contem informações relativas ao usuário denominado representante.
         Tag: Uma chave de um chip RFID que libera a abertura da lixeira ao representante. Ele também é identificado por essa tag
         Nome: Campo que armazena o nome do representante.
         RG: Campo que armazena o RG do representante.
         CPF: Campo que armazena o CPF do representante.
	 Data_nasc: Campo que armazena a data de nascimento do usuário
	 numero_residencia: Campo que armazena o número da residência que o usuário representa
      Dependente: Tabela que armazena dados dos dependentes atrelados ao representante.
         Nome: Campo que armazena o nome do dependente.
         Código: Número unico do dependente de acordo com a quantidade de dependentes atreladas ao representante. Utilizado como chave.
         dat_nasc: Campo que armazena a data de nascimento do dependente.
      Residência: Tabela que armazena informações da residência representada.
         Casa: Campo que armazena o número da residência. Utilizado como chave.
         Tipo_local: Campo que armazena o tipo do local que a residência se encontra.
	 Nome_local: Campo que apresenta o nome do local que a rua se encontra.
      Lixeira: Tabela que armeza as informações de cada lixeira
         Serial: Código único que cada lixeira possui
         Tipo: Armazena o tipo de lixo que cada lixeira carrega
         Peso: Armazena o peso atual da lixeira
     Agendamento
         Protcolo: Código único de cada agendamento
         Horário: campo que armazena a hora na qual o coletor agendado vai passar
         Tipo de lixo produzido:campo qie armazena o tipo de lixo no qual deve-se agendar o coletor correspondente
         Coletores requisitados: campo que armazena os coletores que foram agendados
     Coletores:
          Código do coletor: campo que armazena o codigo unico do coletor que sera usado para que o coletor seja agendado.
          Peso Atual: campo que armazena o peso atual de um certo coletor, para verificar se um agendamento pode ser atendido por este
          Nome_local: campo que armazena o nome do local atual do coletor, para verificar se este pode atender certo agendamento.
	  Tipo_local: Campo que armazena o tipo do local em que o coletor se encontra.
          
       
### 6	MODELO LÓGICO<br>
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/logiquinho.png?raw=true "Modelo Lógico") 


### 7	MODELO FÍSICO<br>
	/* Drop */

	DROP TABLE IF EXISTS USUARIO_LIXEIRA;
	DROP TABLE IF EXISTS COLETOR_LIXEIRA;
	DROP TABLE IF EXISTS LIXEIRA;
	DROP TABLE IF EXISTS COLETOR;
	DROP TABLE IF EXISTS CENTRO_COLETA;
	DROP TABLE IF EXISTS TIPO_LIXO;	
	DROP TABLE IF EXISTS DEPENDENTE;
	DROP TABLE IF EXISTS RELACAO;
	DROP TABLE IF EXISTS USUARIO;
	DROP TABLE IF EXISTS GENERO;
	DROP TABLE IF EXISTS LOCAL;
	DROP TABLE IF EXISTS TIPO_LOCAL;

/* Lógico WITE: */

CREATE TABLE USUARIO (
    tag integer PRIMARY KEY,
    rg integer,
    cpf varchar,
    nome varchar,
    data_nasc date,
    genero integer,
    numero_residencia integer,
    localizacao integer
);

CREATE TABLE DEPENDENTE (
    codigo integer PRIMARY KEY,
    nome varchar,
    data_nasc date,
    genero integer,
    usuario_resp integer,
    relacao integer
);

CREATE TABLE LIXEIRA (
    serial integer PRIMARY KEY,
    peso_atual float,
    peso_total float,
    localizacao integer,
    tipo_lixo integer
);

CREATE TABLE GENERO (
    codigo integer PRIMARY KEY,
    descricao char
);

CREATE TABLE RELACAO (
    codigo integer PRIMARY KEY,
    parentesco varchar
);

CREATE TABLE TIPO_LIXO (
    codigo integer PRIMARY KEY,
    lixo varchar
);

CREATE TABLE COLETOR (
    codigo integer PRIMARY KEY,
    peso_atual float,
    peso_total float,
    latitude varchar,
    longitude varchar,
    vaga_cc integer,
    tipo_lixo integer
);

CREATE TABLE CENTRO_COLETA (
    vaga integer PRIMARY KEY,
    setor integer
);

CREATE TABLE LOCAL (
    codigo integer PRIMARY KEY,
    nome_local varchar,
    tipo_local integer,
    latitude varchar,
    longitude varchar
);

CREATE TABLE TIPO_LOCAL (
    codigo integer PRIMARY KEY,
    tipo varchar
);

CREATE TABLE COLETOR_LIXEIRA (
    lixeira integer,
    coletor integer,
    horario time,
    data date
);

CREATE TABLE USUARIO_LIXEIRA (
    tag_usuario integer,
    lixeira integer,
    horario time,
    data date
);
 
ALTER TABLE USUARIO ADD CONSTRAINT FK_USUARIO_2
    FOREIGN KEY (genero)
    REFERENCES GENERO (codigo)
    ON DELETE CASCADE;
 
ALTER TABLE USUARIO ADD CONSTRAINT FK_USUARIO_3
    FOREIGN KEY (localizacao)
    REFERENCES LOCAL (codigo)
    ON DELETE RESTRICT;
 
ALTER TABLE DEPENDENTE ADD CONSTRAINT FK_DEPENDENTE_2
    FOREIGN KEY (usuario_resp)
    REFERENCES USUARIO (tag)
    ON DELETE CASCADE;
 
ALTER TABLE DEPENDENTE ADD CONSTRAINT FK_DEPENDENTE_3
    FOREIGN KEY (genero)
    REFERENCES GENERO (codigo)
    ON DELETE CASCADE;
 
ALTER TABLE DEPENDENTE ADD CONSTRAINT FK_DEPENDENTE_4
    FOREIGN KEY (relacao)
    REFERENCES RELACAO (codigo)
    ON DELETE CASCADE;
 
ALTER TABLE LIXEIRA ADD CONSTRAINT FK_LIXEIRA_2
    FOREIGN KEY (localizacao)
    REFERENCES LOCAL (codigo)
    ON DELETE RESTRICT;
 
ALTER TABLE LIXEIRA ADD CONSTRAINT FK_LIXEIRA_3
    FOREIGN KEY (tipo_lixo)
    REFERENCES TIPO_LIXO (codigo)
    ON DELETE CASCADE;
 
ALTER TABLE COLETOR ADD CONSTRAINT FK_COLETOR_2
    FOREIGN KEY (vaga_cc)
    REFERENCES CENTRO_COLETA (vaga)
    ON DELETE RESTRICT;
 
ALTER TABLE COLETOR ADD CONSTRAINT FK_COLETOR_3
    FOREIGN KEY (tipo_lixo)
    REFERENCES TIPO_LIXO (codigo)
    ON DELETE CASCADE;
 
ALTER TABLE LOCAL ADD CONSTRAINT FK_LOCAL_2
    FOREIGN KEY (tipo_local)
    REFERENCES TIPO_LOCAL (codigo)
    ON DELETE CASCADE;
 
ALTER TABLE COLETOR_LIXEIRA ADD CONSTRAINT 

FK_COLETOR_LIXEIRA_1
    FOREIGN KEY (lixeira)
    REFERENCES LIXEIRA (serial)
    ON DELETE RESTRICT;
 
ALTER TABLE COLETOR_LIXEIRA ADD CONSTRAINT 

FK_COLETOR_LIXEIRA_2
    FOREIGN KEY (coletor)
    REFERENCES COLETOR (codigo)
    ON DELETE SET NULL;
 
ALTER TABLE USUARIO_LIXEIRA ADD CONSTRAINT 

FK_USUARIO_LIXEIRA_1
    FOREIGN KEY (tag_usuario)
    REFERENCES USUARIO (tag)
    ON DELETE SET NULL;
 
ALTER TABLE USUARIO_LIXEIRA ADD CONSTRAINT 

FK_USUARIO_LIXEIRA_2
    FOREIGN KEY (lixeira)
    REFERENCES LIXEIRA (serial)
    ON DELETE SET NULL;
    
### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
 
#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELA E INSERÇÃO DOS DADOS

 Link do arquivo com as inserções no colab: https://colab.research.google.com/drive/1GBz6k8r0AdMECqSUXCkF2jOOtDI4QJ2K

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
  
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>
	select * from lixeira
	select * from usuario
	select * from dependente
	select * from coletor
	select * from local
	select * from centro_coleta
	select * from genero
	select * from relacao
	select * from tipo_local
	select * from tipo_lixo	

#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)
	
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/where1.png?raw=true "where 1")
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/where2.png?raw=true "where 2")
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/where3.png?raw=true "where 3")
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/where4.png?raw=true "where 4")
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/where5.png?raw=true "where 5") 

		
#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
   Lógicos
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/logic1.png?raw=true "Lógico 1")
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/logic2.png?raw=true "Lógico 2")
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/logic3.png?raw=true "Lógico 3")
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/logic4.png?raw=true "Lógico 4")
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/logic5.png?raw=true "Lógico 5")

Aritimético e renomeação
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/arit1.png?raw=true "Aritimético e renomeação 1")
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/arit2.png?raw=true "Aritimético e renomeação 2")
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/arit3.png?raw=true "Aritimético e renomeação 3")

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


        
        


    





