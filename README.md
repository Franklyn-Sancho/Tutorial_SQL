<h1 align="center"> Um pouco mais sobre SQL </h1>
A alma do Backend é o nosso tão amado banco de dados, saber trabalhar com SQL e noSQL é essencial para aqueles que almejam trabalhar com desenvolvimento Backend. Sem mais delongas, vamos iniciar. 

<h5 align="center"> Antes de tudo, irei disponibilizar algumas ferramentas online para que vocês possam estudar e se divertir, caso não possam instalar as ferramentas necessárias.  </h5>

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
```

CREATE DATABASE NomeDesejado; 
```
***2.1.2. Mostrar todos os dataBases criados*** 
```
SHOW DATABASES; 
```
**2.1.3. Excluir um database:**
obs. Substitua o NomeDesejado, pelo database que deseja excluir
```
DROP DATABASE NomeDesejado;
```
### 2.2. Criando nossas tabelas<br>
Primeiro precisamos chamar a nossa database com o seguinte comando:
```
USE DATABASE NomeDesejado;
```
**2.2.2. Criando a Tabela**<br>
Obs. Aqui iremos chamar o comando de criação de tabela e também adicionar os atributos importantes. Então vou usar um exemplo aleatório
```
CREATE TABLE Curso (
  id varchar(02),
  nome varchar(30),
  local varchar(20),
  estudantes(3)
);
```
Aqui foi criado uma tabela dentro daquele database que criamos, a tabela se chama curso e ela tem seguintes atributos: Id, Nome, Local, Estudantes. Varchar seria como a nossa string, podemos colocar letras e números. Já o Número entre parenteses é a quantidade de caractereses que podemos adicionar neste atributo. Por exemplo: Ao adicionar registro para 'nome', por exemplo, matemática, é necessário que a palavra tenha no máximo 30 caracteres.
