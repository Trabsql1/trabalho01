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

> Nosso sistema conterá as informações descritas a seguir. A respeito da residência serão armazenados, nome da rua e número da casa. A respeito dos dependentes temos a quantidade destes, sua relação com o representante, seu gênero e seu nome. A respeito do representante serão armazenados nome completo, cpf ,rg e uma tag única para cada representante que confere a ele e seus dependentes acesso às lixeiras. A respeito dos coletores tipo de lixo a ser recolhido(orgânico, reciclável, pilhas e bateria, e médicos), o local atual do coletor e o peso que, é claro, diz quanto de lixo o coletor já possui em seu interior. O agendamento é um caso a parte, que ocorre quando um morador chama um coletor específico diretamente a sua casa. Isso é incrívelmente útil nos casos de eventos e confraternizações, afim de não sobrecarregar a lixeira comunitária. 
Cada coletor pode ser direcionado a mais de um agendamento após o término de seu quarteirão padrão, e caso um não termine sua coleta ele pode retornar ou outro coletor disponível será enviado. Após terminarem sua rota designada ou atingirem capacidade máxima os coletores se dirigirão para o centro de eliminação. Lixo reciclável será reciclado e lixo orgânico será enviado ao centro de compostagem e transformado em fertilizante orgânico, pílhas e baterias serão descartadas no centro de coleta,e lixo hospitalar será incinerado.   Todos os dados podem ser alterados caso o usuário requisite e é imprescindível a atualização dos dados de forma correta para evitar problemas.


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
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/Conc.jpg?raw=true "Modelo Conceitual")      
    
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
![Alt text](https://github.com/Trabsql1/trabalho01/blob/master/ligma.jpg?raw=true "Modelo Lógico") 


### 7	MODELO FÍSICO<br>
/* Lógico_3: */

CREATE TABLE Usuario (
    Tag Integer PRIMARY KEY,
    Nome Varchar,
    RG Varchar,
    CPF Varchar,
    fk_Dependentes_Codigo Integer
);

CREATE TABLE Coletores (
    Codigo_do_Coletor Integer PRIMARY KEY,
    Peso_Atual Double,
    Tipo_Local Varchar,
    Nome_Local Varchar
);

CREATE TABLE Residencia (
    Casa Integer PRIMARY KEY,
    Tipo_Local Varchar,
    Nome_Local Varchar,
    fk_Coletores_Codigo_do_Coletor Integer
);

CREATE TABLE Dependentes (
    Relacao Varchar,
    Idade Integer,
    Genero Varchar,
    Nome Varchar,
    Codigo Integer PRIMARY KEY
);

CREATE TABLE Lixeira (
    Tipo Varchar,
    Peso Double,
    Serial Integer PRIMARY KEY
);

CREATE TABLE Agenda (
    fk_Usuario_Tag Integer,
    fk_Coletores_Codigo_do_Coletor Integer,
    Protocolo Varchar PRIMARY KEY,
    Horario Time,
    Tipo_Lixo Varchar,
    Coletor_requisitado Varchar
);

CREATE TABLE Acessa (
    fk_Lixeira_Serial Integer,
    fk_Usuario_Tag Integer
);
 
ALTER TABLE Usuario ADD CONSTRAINT FK_Usuario_2
    FOREIGN KEY (fk_Dependentes_Codigo)
    REFERENCES Dependentes (Codigo)
    ON DELETE CASCADE;
 
ALTER TABLE Residencia ADD CONSTRAINT FK_Residencia_2
    FOREIGN KEY (fk_Coletores_Codigo_do_Coletor)
    REFERENCES Coletores (Codigo_do_Coletor)
    ON DELETE CASCADE;
 
ALTER TABLE Agenda ADD CONSTRAINT FK_Agenda_2
    FOREIGN KEY (fk_Usuario_Tag)
    REFERENCES Usuario (Tag)
    ON DELETE RESTRICT;
 
ALTER TABLE Agenda ADD CONSTRAINT FK_Agenda_3
    FOREIGN KEY (fk_Coletores_Codigo_do_Coletor)
    REFERENCES Coletores (Codigo_do_Coletor)
    ON DELETE SET NULL;
 
ALTER TABLE Acessa ADD CONSTRAINT FK_Acessa_1
    FOREIGN KEY (fk_Lixeira_Serial)
    REFERENCES Lixeira (Serial)
    ON DELETE SET NULL;
 
ALTER TABLE Acessa ADD CONSTRAINT FK_Acessa_2
    FOREIGN KEY (fk_Usuario_Tag)
    REFERENCES Usuario (Tag)
    ON DELETE SET NULL;
    
### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES

insert into Agenda
values('1','1','123456789', '2019-12-10','Organico','1'
	'2','1','90876452', '2019-12-10','reciclavel','2'
	'3','1','10101010', '2019-12-11','Baterias','3'
	):

insert into dependentes
values('Filho','1','M', '1','Jonas','1'
	'Esposa','24','F', '1','Luiz','2'
	'Filho','3','M', 'Lucas','1'):

insert into coletores
values('10','1','R. das Salivas','2'
	'0','2','R. das Salivas','1'
	'10','3','R. das Salivas','2');

insert into lixeira
values('Organico','10','0'
	'Reciclavel','0','1'
	'Baterias','10','3');


insert into residencia
values('1','R. das Flores'
	'2','R. das Flores'
	'3','R. das Dalilas');

insert into usuario
values('123.456.789-00','12.3456-ES','1','Marcos'
	'113.436.709-00','13.1456-ES','2','Lucas'
	'123.456.789-00','12.3456-ES','3','Sazam');
 
#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELA E INSERÇÃO DOS DADOS

CREATE TABLE Usuario (
    CPF varchar,
    RG varchar,
    Tag integer PRIMARY KEY,
    Nome varchar
);

CREATE TABLE Residencia (
    Casa integer PRIMARY KEY,
    Rua varchar,
    fk_Coletores_Codigo_do_Coletor integer
);

CREATE TABLE Lixeira (
    Tipo varchar,
    Peso float,
    Serial integer PRIMARY KEY
);

CREATE TABLE Coletores (
    Peso_Atual float,
    Codigo_do_Coletor integer PRIMARY KEY,
    Posicao_atual varchar,
    Quarteirao_Atribuido integer
);

CREATE TABLE Dependentes (
    Relacao varchar,
    Idade integer,
    Genero character,
    Codigo integer PRIMARY KEY,
    Nome varchar,
    fk_Usuario_Tag integer
);

CREATE TABLE Acessa (
    fk_Lixeira_Serial integer,
    fk_Usuario_Tag integer
);

CREATE TABLE Agenda (
    fk_Usuario_Tag integer,
    fk_Coletores_Codigo_do_Coletor integer,
    Protocolo integer PRIMARY KEY,
    Horario date,
    Tipo_Lixo varchar,
    Coletor_requisitado integer
);
 
ALTER TABLE Residencia ADD CONSTRAINT FK_Residencia_2
    FOREIGN KEY (fk_Coletores_Codigo_do_Coletor)
    REFERENCES Coletores (Codigo_do_Coletor)
    ON DELETE CASCADE;
 
ALTER TABLE Dependentes ADD CONSTRAINT FK_Dependentes_2
    FOREIGN KEY (fk_Usuario_Tag)
    REFERENCES Usuario (Tag)
    ON DELETE CASCADE;
 
ALTER TABLE Acessa ADD CONSTRAINT FK_Acessa_1
    FOREIGN KEY (fk_Lixeira_Serial)
    REFERENCES Lixeira (Serial)
    ON DELETE RESTRICT;
 
ALTER TABLE Acessa ADD CONSTRAINT FK_Acessa_2
    FOREIGN KEY (fk_Usuario_Tag)
    REFERENCES Usuario (Tag)
    ON DELETE RESTRICT;
 
ALTER TABLE Agenda ADD CONSTRAINT FK_Agenda_2
    FOREIGN KEY (fk_Usuario_Tag)
    REFERENCES Usuario (Tag)
    ON DELETE SET NULL;
 
ALTER TABLE Agenda ADD CONSTRAINT FK_Agenda_3
    FOREIGN KEY (fk_Coletores_Codigo_do_Coletor)
    REFERENCES Coletores (Codigo_do_Coletor)
    ON DELETE SET NULL;

insert into Agenda
values('1','1','123456789', '2019-12-10','Organico','1'
	'2','1','90876452', '2019-12-10','reciclavel','2'
	'3','1','10101010', '2019-12-11','Baterias','3'
	);

insert into dependentes
values('Filho','1','M', '1','Jonas','1'
	'Esposa','24','F', '1','Luiz','2'
	'Filho','3','M', 'Lucas','1');

insert into coletores
values('10','1','R. das Salivas','2'
	'0','2','R. das Salivas','1'
	'10','3','R. das Salivas','2')

insert into lixeira
values('Organico','10','0'
	'Reciclavel','0','1'
	'Baterias','10','3');


insert into residencia
values('1','R. das Flores'
	'2','R. das Flores'
	'3','R. das Dalilas');

insert into usuario
values('123.456.789-00','12.3456-ES','1','Marcos'
	'113.436.709-00','13.1456-ES','2','Lucas'
	'123.456.789-00','12.3456-ES','3','Sazam');
#### 8.3 INCLUSÃO DO SCRIPT PARA EXCLUSÃO DE TABELAS EXISTENTES, CRIAÇÃO DE TABELA NOVAS E INSERÇÃO DOS DADOS
     DROP TABLE usuario;
     DROP TABLE residencia;
     DROP TABLE lixeira;
     DROP TABLE dependentes;
     DROP TABLE acessa;
     DROP TABLE agenda;
     
     CREATE TABLE Usuario (
    CPF varchar,
    RG varchar,
    Tag integer PRIMARY KEY,
    Nome varchar
);

CREATE TABLE Residencia (
    Casa integer PRIMARY KEY,
    Rua varchar,
    fk_Coletores_Codigo_do_Coletor integer
);

CREATE TABLE Lixeira (
    Tipo varchar,
    Peso float,
    Serial integer PRIMARY KEY
);

CREATE TABLE Coletores (
    Peso_Atual float,
    Codigo_do_Coletor integer PRIMARY KEY,
    Posicao_atual varchar,
    Quarteirao_Atribuido integer
);

CREATE TABLE Dependentes (
    Relacao varchar,
    Idade integer,
    Genero character,
    Codigo integer PRIMARY KEY,
    Nome varchar,
    fk_Usuario_Tag integer
);

CREATE TABLE Acessa (
    fk_Lixeira_Serial integer,
    fk_Usuario_Tag integer
);

CREATE TABLE Agenda (
    fk_Usuario_Tag integer,
    fk_Coletores_Codigo_do_Coletor integer,
    Protocolo integer PRIMARY KEY,
    Horario date,
    Tipo_Lixo varchar,
    Coletor_requisitado integer
);
 
ALTER TABLE Residencia ADD CONSTRAINT FK_Residencia_2
    FOREIGN KEY (fk_Coletores_Codigo_do_Coletor)
    REFERENCES Coletores (Codigo_do_Coletor)
    ON DELETE CASCADE;
 
ALTER TABLE Dependentes ADD CONSTRAINT FK_Dependentes_2
    FOREIGN KEY (fk_Usuario_Tag)
    REFERENCES Usuario (Tag)
    ON DELETE CASCADE;
 
ALTER TABLE Acessa ADD CONSTRAINT FK_Acessa_1
    FOREIGN KEY (fk_Lixeira_Serial)
    REFERENCES Lixeira (Serial)
    ON DELETE RESTRICT;
 
ALTER TABLE Acessa ADD CONSTRAINT FK_Acessa_2
    FOREIGN KEY (fk_Usuario_Tag)
    REFERENCES Usuario (Tag)
    ON DELETE RESTRICT;
 
ALTER TABLE Agenda ADD CONSTRAINT FK_Agenda_2
    FOREIGN KEY (fk_Usuario_Tag)
    REFERENCES Usuario (Tag)
    ON DELETE SET NULL;
 
ALTER TABLE Agenda ADD CONSTRAINT FK_Agenda_3
    FOREIGN KEY (fk_Coletores_Codigo_do_Coletor)
    REFERENCES Coletores (Codigo_do_Coletor)
    ON DELETE SET NULL;

insert into Agenda
values('1','1','123456789', '2019-12-10','Organico','1'
	'2','1','90876452', '2019-12-10','reciclavel','2'
	'3','1','10101010', '2019-12-11','Baterias','3'
	);

insert into dependentes
values('Filho','1','M', '1','Jonh','1'
	'Esposa','24','F', '1','Luana','2'
	'Filho','3','M', 'Marcox','1');

insert into coletores
values('10','1','R. das Salivas','2'
	'0','2','R. das Salivas','1'
	'10','3','R. das Salivas','2);

insert into lixeira
values('Organico','10','0'
	'Reciclavel','0','1'
	'Baterias','10','3'):


insert into residencia
values('1','R. das Flores'
	'2','R. das Flores'
	'3','R. das Dalilas'):

insert into usuario
values('123.456.789-00','12.3456-ES','1','Marcos'
	'113.436.709-00','13.1456-ES','2','Lucas'
	'123.456.789-00','12.3456-ES','3','Sazam'):

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


        
        


    





