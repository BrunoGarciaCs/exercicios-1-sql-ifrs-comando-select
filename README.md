
🗄️ Prática de Banco de Dados: Lista de Exercícios em SQL (Módulo II)

Este repositório contém a segunda lista de exercícios práticos em SQL, desenvolvida como forma de reforço e fixação de conteúdos para o curso de Administrador de Banco de Dados pelo Instituto Federal do Rio Grande do Sul (IFRS).

🎯 Objetivo do Arquivo

O objetivo deste documento é registrar o avanço prático no aprendizado de manipulação e consulta de dados relacionais. Para potencializar os estudos, utilizei Inteligência Artificial para a criação de cenários e enunciados realistas de banco de dados (envolvendo tabelas de clientes, produtos, pedidos, chamados e usuários), permitindo praticar a escrita e estruturação manual de queries SQL.



🛠️ Comandos e Conceitos Praticados

Nesta lista, foram trabalhados comandos fundamentais para filtragem e seleção avançada de dados na cláusula WHERE:
SELECT ... FROM ... AS: Projeção de colunas específicas e uso de aliases para nomenclatura e legibilidade.

Operadores Relacionais e Comparação Numérica (=, <): Filtragem condicional exata e comparações matemáticas.

Operadores Lógicos (AND, OR): Combinação de múltiplas condições de seleção.
IN / NOT IN: Filtragem por inclusão e exclusão dentro de conjuntos de valores.
LIKE (Com caracteres coringa %):
Sufixo (%termo): Busca de palavras que terminam com um padrão (ex: e-mails @gmail.com).
Prefixo (termo%): Busca de palavras que começam com um padrão (ex: produtos iniciando em 'Cabo').
Substring (%termo%): Busca de padrões situados em qualquer parte do texto.

📝 Enunciados e Soluções SQL

01. Filtro por Valor Exato (Texto)

Enunciado: Considere a tabela produtos com as colunas id, nome, categoria, preco e quantidade_estoque. Qual seria a consulta para saber o nome e o preço de todos os produtos que pertencem à categoria 'Eletrônicos'?

SELECT prod.nome, prod.preco
FROM produtos AS prod
WHERE prod.categoria = 'Eletrônicos';


02. Filtro por Comparação Numérica

Enunciado: Considere a tabela produtos com as colunas id, nome, categoria, preco e quantidade_estoque. Qual seria a consulta para saber o nome e a quantidade em estoque de todos os produtos que possuem estoque menor que 10 unidades?

SELECT prod.nome, prod.quantidade_estoque 
FROM produtos AS prod
WHERE prod.quantidade_estoque < 10;


03. Filtro Múltiplo com AND

Enunciado: Considere a tabela clientes com as colunas id, nome, cidade, estado e ativo. Qual seria a consulta para saber o nome e a cidade de todos os clientes que moram no estado 'SP' e estão com o cadastro 'Ativo'?

SELECT cli.nome, cli.cidade
FROM clientes AS cli
WHERE cli.estado = 'SP' AND cli.ativo = 'Ativo';


04. Filtro Alternativo com OR / IN

Enunciado: Considere a tabela chamados com as colunas id, descricao, prioridade, status e atendente. Qual seria a consulta para saber o id e a descrição de todos os chamados que têm prioridade 'Alta' ou prioridade 'Urgente'?

SELECT ch.id, ch.descricao
FROM chamados AS ch
WHERE ch.prioridade IN ('Alta', 'Urgente');


05. Filtro de Padrão de Texto com LIKE (Sufixo)

Enunciado: Considere a tabela alunos com as colunas id, nome, curso e email. Qual seria a consulta para saber o nome e o e-mail de todos os alunos cujo e-mail termina com '@gmail.com'?

SELECT alu.nome, alu.email
FROM alunos AS alu
WHERE alu.email LIKE '%@gmail.com';


06. Filtro Negativo com NOT IN

Enunciado: Considere a tabela funcionarios com as colunas id, nome, departamento, cargo e salario. Qual seria a consulta para saber o nome e o departamento de todos os funcionários que não pertencem aos departamentos 'RH', 'Marketing' e 'Financeiro'?

SELECT func.nome, func.departamento
FROM funcionarios AS func
WHERE func.departamento NOT IN ('RH', 'Marketing', 'Financeiro');


07. Busca por Prefixo com LIKE

Enunciado: Considere a tabela produtos com as colunas id, nome, categoria, codigo_barras e preco. Qual seria a consulta para saber o nome e o código de barras de todos os produtos cujo nome começa com a palavra 'Cabo'?

SELECT prod.nome, prod.codigo_barras
FROM produtos AS prod
WHERE prod.nome LIKE 'Cabo%';


08. Lista de Opções com IN

Enunciado: Considere a tabela pedidos com as colunas id_pedido, cliente_id, status, valor_total e forma_pagamento. Qual seria a consulta para saber o id do pedido e o valor total dos pedidos cuja forma de pagamento seja 'PIX', 'Boleto' ou 'Cartão de Crédito'?

SELECT ped.id_pedido, ped.valor_total
FROM pedidos AS ped
WHERE ped.forma_pagamento IN ('PIX', 'Boleto', 'Cartão de Crédito');


09. Busca por Trecho de Texto com LIKE

Enunciado: Considere a tabela livros com as colunas id, titulo, autor, editora e ano_publicacao. Qual seria a consulta para saber o título e o autor de todos os livros que contêm a palavra 'Dados' em qualquer parte do título?

SELECT li.titulo, li.autor
FROM livros AS li
WHERE li.titulo LIKE '%Dados%';


10. Combinação de LIKE com NOT IN

Enunciado: Considere a tabela usuarios com as colunas id, nome, email, perfil e status. Qual seria a consulta para saber o nome e o e-mail de todos os usuários cujo perfil não seja nem 'Admin' nem 'Suporte', e o nome termine com o sobrenome 'Silva'?

SELECT usu.nome, usu.email
FROM usuarios AS usu
WHERE usu.perfil NOT IN ('Admin', 'Suporte') 
  AND usu.nome LIKE '%Silva';


👨‍💻 Autor: Estudante do Curso de Administrador de Banco de Dados - IFRS.

📌 Repositório focado no aprendizado contínuo de SQL e Gestão de Bancos de Dados.
