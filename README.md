<h1 align="center"> Um pouco mais sobre SQL </h1>
A alma do Backend é o nosso tão amado banco de dados, saber trabalhar com SQL e NoSQL é essencial para aqueles que almejam trabalhar com desenvolvimento Backend. Sem mais delongas, Bora codar. 

<h5 align="center"> Antes de tudo, irei disponibilizar algumas ferramentas online para que vocês possam estudar e se divertir, se por algum motivo não puderem instalar os softwares necessários  </h5>

## 1. Então antes de qualquer coisa 
1.2. **Vamos às ferramentas:**

   * https://sqliteonline.com
   * http://sqlfiddle.com/

1.2. **Artigos importantes**

   * Artigo da Wikipédia sobre a nossa protagonista: https://pt.wikipedia.org/wiki/SQL
   * Instação do PostgreSQL: https://rockcontent.com/br/blog/postgresql/
   * Também temos o MySql, Sql Server, Oracle e etc.
   * Leia também sobre NoSQL: MondoDB e etc.

## 2. Agora sim é SQL 

O SQL funciona por comandos, exatamente como o terminal do nosso computador. Mas não precisa ficar assustado, é tudo muito simples. Ok, nem tanto assim, mas se você entender os conceitos e praticar todos os dias, ao lidar com algo complexo, não serão tão complexos assim. Agora vamos seguir o nosso trabalho:<br><br>
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
**2.2.2. Agora sim, nossa primeira tabela**<br>
Obs. Aqui iremos chamar o comando de criação de tabela e também adicionar os atributos importantes. Para facilitar o entendimento, vou criar uma tabela aleatória:
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
**2.3.2. Atualizando registros em nossa tabela**<br>
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

**2.3.3. Removendo registros da nossa tabela:**
Se for necessário remover alguma registro, no caso uma linha, basta executar este comando logo abaixo
```sql
DELETE FROM Nome_tabela
WHERE IdentificadorRegistro
```
vamos ao exemplo pra facilitar:
```sql
DELETE FROM cursos
WHERE id=03
```
Depois de executar esse comando, o curso 'sistemas operacionais' será removido da nossa tabela.

**2.4. Vamos as subconsultas**
<p> A subconsulta é um tipo de select mais específico. Diferente do que aprendemos no capítulo **2.3**, agora vamos aprender a  trabalhar com os tratamentos: any, in, all, exists. Podemos resumir a subconsulta como um select entre tabelas. Darei alguns exemplos de comandos, mas preciso reforçar que neste caso, o comando certo depende unicamente da lógica do seu banco de dados. </p>
<p> Amo construir os meus exemplos, mas pela extensão do assunto, principalmente pela lógica, deixarei alguns links para que vocês possam estudar </p>

1. Link: http://www.inf.ufsc.br/~r.mello/ine5323/SQL-subconsultas.pdf<br>
2. Link: https://imasters.com.br/back-end/como-fazer-subconsultas-um-passo-passo<br>
3. Link: https://www.ibm.com/support/knowledgecenter/pt-br/SS9UMF_11.2.0/ugr/ugr/tpc/dsq_create_subquery_retrieve_data.html
mas para não perder o costume, deixarei a carinha de uma subconsulta aqui:

```sql
SELECT ǹome, sobrenome FROM clientes WHERE id =
(SELECT id FROM clientes WHERE sobrenome = 'Silva');
```

ParaCegoVer: Selecione o nome e o sobrenome da tabela clientes onde o id desse tal cliente tenha como sobrenome o registro Silva :smile:



