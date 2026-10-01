
01. Filtro por Valor Exato (Texto)
Considere a tabela produtos com as colunas id, nome, categoria, preco e quantidade_estoque. Qual seria a consulta para saber
o nome e o preco de todos os produtos que pertencem à categoria 'Eletrônicos'?

SELECT prod.nome, prod.preco
FROM produtos AS prod
WHERE prod.categoria = 'Eletrônicos';

---------------------------------------------------------------------------------------------------------------------------

02. Filtro por Comparação Numérica
Considere a tabela produtos com as colunas id, nome, categoria, preco e quantidade_estoque. Qual seria a consulta para saber
o nome e a quantidade_estoque de todos os produtos que possuem estoque menor que 10 unidades?

SELECT prod.nome, prod.quantidade_estoque 
FROM produtos AS prod
WHERE prod.quantidade_estoque < 10;

---------------------------------------------------------------------------------------------------------------------------

03. Filtro Múltiplo com AND
Considere a tabela clientes com as colunas id, nome, cidade, estado e ativo. Qual seria a consulta para saber o nome e a 
cidade de todos os clientes que moram no estado 'SP' e estão com o cadastro 'Ativo'?

SELECT cli.nome, cli.cidade
FROM clientes AS cli
WHERE cli.estado = 'SP' AND cli.ativo = 'Ativo';

---------------------------------------------------------------------------------------------------------------------------

04. Filtro Alternativo com OR
Considere a tabela chamados com as colunas id, descricao, prioridade, status e atendente. Qual seria a consulta para saber 
o id e a descricao de todos os chamados que têm prioridade 'Alta' ou prioridade 'Urgente'?

SELECT ch.id, ch.descricao
FROM chamados AS ch
WHERE ch.prioridade IN ('Alta', 'Urgente');

---------------------------------------------------------------------------------------------------------------------------

05. Filtro de Padrão de Texto com LIKE
Considere a tabela alunos com as colunas id, nome, curso e email. Qual seria a consulta para saber o nome e o email de todos
 os alunos cujo e-mail termina com '@gmail.com'?

SELECT alu.nome, alu.email
FROM alunos AS alu
WHERE alu.email LIKE '%@gmail.com';

---------------------------------------------------------------------------------------------------------------------------

06. Filtro Negativo com NOT IN
Considere a tabela funcionarios com as colunas id, nome, departamento, cargo e salario. Qual seria a consulta para saber o nome e o 
departamento de todos os funcionários que não pertencem aos departamentos 'RH', 'Marketing' e 'Financeiro'?

SELECT func.nome, func.departamento
FROM funcionarios.func
WHERE func.cargo NOT IN ('RH', 'Marketing', 'Financeiro');

---------------------------------------------------------------------------------------------------------------------------

07. Busca por Prefixo com LIKE
Considere a tabela produtos com as colunas id, nome, categoria, codigo_barras e preco. Qual seria a consulta para saber o nome e o 
codigo_barras de todos os produtos cujo nome começa com a palavra 'Cabo'?

SELECT prod.nome, prod.codigo_barras
FROM produtos AS prod
WHERE prod.nome LIKE 'Cabo%';

---------------------------------------------------------------------------------------------------------------------------

08. Lista de Opções com IN
Considere a tabela pedidos com as colunas id_pedido, cliente_id, status, valor_total e forma_pagamento. Qual seria a consulta para saber o 
id do pedido e o valor total dos pedidos cuja forma de pagamento seja 'PIX', 'Boleto' ou 'Cartão de Crédito'?

SELECT ped.id_pedido, ped.valor_total
FROM pedidos AS ped
WHERE prod.forma_pagamento IN ('PIX','Boleto', 'Cartão de Crédito');

---------------------------------------------------------------------------------------------------------------------------

09. Busca por Trecho de Texto com LIKE
Considere a tabela livros com as colunas id, titulo, autor, editora e ano_publicacao. Qual seria a consulta para saber o titulo e o autor de todos 
os livros que contêm a palavra 'Dados' em qualquer parte do título?

SELECT li.titulo, li.autor
FROM livros AS li
WHERE li.titulo LIKE ('%Dados%');

---------------------------------------------------------------------------------------------------------------------------

10. Combinação de LIKE com NOT IN
Considere a tabela usuarios com as colunas id, nome, email, perfil e status. Qual seria a consulta para saber o nome e o email de todos os usuários 
cujo perfil não seja nem 'Admin' nem 'Suporte', e o nome termine com o sobrenome 'Silva'?

SELECT usu.nome, usu.email
FROM usuarios AS usu
WHERE usu.perfil NOT IN ('Admin', 'Suporte') 
AND usu.nome LIKE '%Silva';
