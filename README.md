# Algumas anotações importantes para estudar Banco de Dados e utilizar como consulta


-- Autor: Rhael Henrique

------------------------------------------------------------------------

:: Comando de Criar Tabela

CREATE TABLE tabela1 (id_tabela1 INT PRIMARY KEY, nome_tabela1 VARCHAR(255));

--Cada campo deve ter o seu tipo determinado. Note que o ID será a Chave Primária e vai ser preenchido automaticamente.

:: Comando de Deletar campo da tabela

ALTER TABLE tabela1 DROP campo1;

--Vai deletar o campo especificado da tabela especificada.

:: Comando Adicionar um campo na tabela

ALTER TABLE tabela1 ADD campo3 INT(20) NOT NULL AFTER campo2;

--Vai adicionar o campo3 dentro da tabela1, logo após o campo2;

:: Comando para Deletar uma tabela

DROP TABLE tabela1;

--Vai deletar por completo a tabela especificada.

:: Comando de Inserção de dados

INSERT INTO tabela1 (campo1, campo2) VALUES ('valor1', 'valor2');

--Vai fazer a inserção na tabela1, dentro dos campo1 e campo2, os valores valor1 e valor2;

:: Comando de Busca

SELECT campo1, campo2 FROM tabela1;

--Vai buscar os registros dos campo1 e campo2 dentro da tabela1.

SELECT * FROM tabela1;

--Vai buscar todos os registros da tabela1.

:: Comando de Busca com filtragem de resultados iguais

SELECT DISTINCT campo1 FROM tabela1;

--Vai buscar dentro da tabela1 os valores que não se repetem no campo1. Vale ressaltar que se você adicionar mais de 1 campo, a função do distinct não será bem aplicada pois ele vai trazer todos os registros dos dois campos, sem fazer a filtragem.

:: Busca com Condição

SELECT campo1, campo2 FROM tabela1 WHERE campo1 'condição';

--Vai buscar no banco, resultados dentro dos campo1 e campo2, da tabela1 que contenham a condição no campo1, passada no WHERE.

:: Operadores de Condição

= != > < >= <= <>

--Mesmas funcionalidades das linguagens de programação.

:: Operadores Lógicos

AND OR NOT

SELECT campo1, campo2 FROM tabela1 WHERE NOT campo1 = 'condição';

--Vai inverter a condição determinada. Por exemplo: WHERE NOT cidade 'Natal';

SELECT campo1, campo2, campo3 FROM tabela1 WHERE (campo1 = 'condição' OR campo2 = 'condição') AND campo3 = 'condição';

--Vai retornar os dados que atendam às condições passadas na consulta. Repare que o OR está dentro de () em seguida vem o AND. Será uma condição OU outra que está dentro do () E a condição após o AND.

SELECT * FROM tabela1 WHERE campo1 = 'condição' AND campo2 = 'condição';

--Aqui as condições dentro do campo1 E campo2 devem ser verdadeiras, para retornar um valor.

SELECT * FROM tabela1 WHERE campo1 IS NOT NULL;

--Vai retornar os dados dentro do campo1 que NÃO são NULOS.
--Removendo o IS, vai mostrar os dados dentro do campo1 que SÃO NULOS.

:: Comando para Ordenar os resultados

SELECT * FROM tabela1 ORDER BY campo1;

--Vai retornar todos os dados da tabela1 Ordenados pelo campo1 (a-z / menor-maior).

SELECT * FROM tabela1 ORDER BY campo1 DESC;

--Nesse caso, vai retornar todos os dados da tabela1 Ordenados pelo campo1 de forma decrescente (z-a / maior-menor);

:: Atualizando dados em uma tabela

UPDATE tabela1 SET campo2 = 'novo valor', campo3 = 'novo valor' WHERE campo1 = identificador;

--Vai atualizar os valores dos campo2 e campo3, para o novo valor, passando como campo identificador o campo1.
--Atenção pois se o campo for de texto, usa as '' mas se for numero não precisa!

UPDATE tabela1 SET campo2 = 'novo valor' WHERE campo2 = 'valor antigo';

--Vai atualizar todos os registros que possuiam o valor antigo no campo2, para o novo valor.

UPDATE tabela1 SET campo2 = 'novo valor' WHERE campo2 = 'valor antigo' AND campo3 = 'condição';

--Nesse caso estamos adicionando mais uma condição para que ele faça a atualização. Desta vez, vai filtrar para atualizar apenas os registros em que o campo2 tenha o valor antigo E também tenha o campo3 com a condição especificada.

DELETE FROM tabela1 WHERE campo1 = identificador;

--Vai Deletar os registros da tabela1 Onde o campo1 = identificador.

DELETE FROM tabela1 WHERE campo2 = 'condição' AND campo3 = 'condição';

--Vai Deletar os registros da tabela1 Onde o campo2 = condição E o campo3 = condição.

    © 2021 GitHub, Inc.
    Terms
    Privacy
    Security
    Status
    Docs

    Contact GitHub
    Pricing
    API
    Training
    Blog
    About

Loading complete
