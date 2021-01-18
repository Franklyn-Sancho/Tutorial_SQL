<h1 align="center"> Um pouco mais sobre SQL </h1>
A alma do Backend é o nosso tão amado banco de dados, saber trabalhar com SQL e noSQL é essencial para aqueles que almejam trabalhar com desenvolvimento Backend. Sem mais delongas, Bora codar. 

<h5 align="center"> Antes de tudo, irei disponibilizar algumas ferramentas online para que vocês possam estudar e se divertir, se por algum morito não puderem instalar as ferramentas e softwares necessários  </h5>

## 1. Então antes de qualquer coisa 
1.2. **Vamos as ferramentas:**

   * https://sqliteonline.com
   * http://sqlfiddle.com/

1.2. **Artigos importantes**

   * Artigo da Wikipédia sobre a nossa protagonista: https://pt.wikipedia.org/wiki/SQL
   * Instação do PostgreSQL: https://rockcontent.com/br/blog/postgresql/
   * Também temos o MySql, Sql Server, Oracle e etc.
   * Leia também sobre NoSQL: MondoDB e etc.

## 2. Agora sim é SQL. 

O SQL funciona por comandos, exatamente como o terminal do nosso computador. Mas não precisa ficar assustado, é tudo muito simples. Ok, nem tanto assim, mas se você entender os conceitos e praticar todos os dias, ao lidar com algo complexo, não serão tão complexo assim. Agora vamos seguir o nosso trabalho:<br><br>
**2.1 Criar o nosso DataBase:**<br>
Obs. Substitua o 'NomeDesejado' por algo que faça sentido no seu negócio
```SQL
CREATE DATABASE NomeDesejado; 
```
**2.1.2. Mostrar todos os dataBases criados**
```SQL
SHOW DATABASES; 
```
**2.1.3. Excluir um database:**
obs. Substitua o NomeDesejado, pelo database que deseja excluir
```SQL
DROP DATABASE NomeDesejado;
```
### 2.2. Criando nossas tabelas<br>
Primeiro precisamos chamar a nossa database com o seguinte comando:
```SQL
USE DATABASE NomeDesejado;
```
**2.2.2. Criando a Tabela**<br>
Obs. Aqui iremos chamar o comando de criação de tabela e também adicionar os atributos importantes. Então vou usar um exemplo aleatório
```SQL
CREATE TABLE Curso (
  id varchar(02),
  nome varchar(30),
  local varchar(20),
  estudantes(3)
);
```
Aqui foi criado uma tabela dentro daquele database que criamos, a tabela se chama curso e ela tem seguintes atributos: Id, Nome, Local, Estudantes. Varchar seria como a nossa string, podemos colocar letras e números. Já o Número entre parenteses é a quantidade de caractereses que podemos adicionar neste atributo. Por exemplo: Ao adicionar registro para 'nome', por exemplo, matemática, é necessário que a palavra tenha no máximo 30 caracteres.

**2.2.3. Listando as nossas tabelas**
```SQL
SHOW TABLES;
```
### 2.3. Selecionando, visualizando, adicionando, atualizando e removendo nossos registros
Se quisermos visualizar todos os dados da nossa tabela, basta colocar o asterisco.
```SQL
SELECT * FROM NomeDaTabela;
```
Agora se quisermos visualizar apenas um campo ou atributo
```SQL
Select NomeCampo FROM NomeDaTabela
```
**2.3.1. Adicionando registros em nossa tabela**<br>
Vamos usar como exemplo a tabela cursos que criamos logo acima. 
```SQL
INSERT INTO Cursos(ID, NOME, LOCAL, ESTUDANTE) VALUES (01, "Banco de dados", "Rio de Janeiro", 20)
INSERT INTO Cursos(ID, NOME, LOCAL, ESTUDANTE) VALUES (02, "Linguagem Python", "São Paulo", 30)
INSERT INTO Cursos(ID, NOME, LOCAL, ESTUDANTE) VALUES (03, "Sistemas Operacionais", "Minas Gerais", 10)
INSERT INTO Cursos(ID, NOME, LOCAL, ESTUDANTE) VALUES (04, "Segurança da informação", "Narnia", 40)
```
Será adicionando 01 na ID (Primary Key, falarei daqui a pouco sobre isso); Banco de dados no atríbuto nome; Rio de Janeiro no Local e 20 em estudantes. Ficaria assim:
ID   | Nome                 | Local        | Estudantes
-----|----------------------|--------------|-----------
01   | Banco de Dados       |Rio de janeiro|20
02   | Linguagem Python     |São Paulo     |30 
03   | Sistemas Operacionais|MInas Gerais  |10
04   | Segunda da informação|Narnia        |40

Também podemos adicionar registros de forma mais resumida. Como no exemplo abaixo:
```SQL
INSERT INTO Cursos VALUES(01,"Banco de dados","Rio de Janeiro",20)
```
**2.3.2. Modificando registros em nossa tabela**<br>
Caso seja necessário modificar ou atualizar os dados de algum registro, basta seguir este comando: 
```SQL
UPDATE NomeTabela
SET CampoDesejado = "Novo_Valor"
WHERE AtributoIdentificador
```
Exemplo:
```SQL
UPDATE CURSOS
Set local = "Mordor"
Where id = 02
```
Ao executar o comando, o registro que tem como ID = 02, no caso linguagem python, terá seu local modificado de São Paulo, para Mordor. Deixando nossa tabela dessa forma: 
ID   | Nome                 | Local        | Estudantes
-----|----------------------|--------------|-----------
01   | Banco de Dados       |Rio de janeiro|20
02   | Linguagem Python     |**Mordor**    |30 
03   | Sistemas Operacionais|MInas Gerais  |10
04   | Segunda da informação|Narnia        |40
