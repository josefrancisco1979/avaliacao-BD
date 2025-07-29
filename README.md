 

 

# 📘 README – Exercícios SQL de Avaliação Escolar

## 🧩 Objetivo do Projeto

Este projeto tem como objetivo a construção e manipulação de um banco de dados escolar, utilizando **consultas SQL estruturadas** para atender critérios avaliativos de aprendizado. Foram utilizados comandos `CREATE`, `INSERT`, `SELECT`, e operadores variados com foco na prática de:

- Consultas condicionais e agrupamentos  
- Funções de agregação e manipulação de datas  
- Operadores aritméticos, lógicos e de comparação  
- Subconsultas e diferentes tipos de `JOIN`

---

## 🏫 Estrutura do Banco

O banco de dados é composto pelas seguintes tabelas:

- `Aluno`: cadastro de estudantes  
- `Professor`: cadastro de docentes  
- `Curso`: definição de cursos oferecidos  
- `Turma`: associação de cursos e professores  
- `Matricula`: registro de alunos em turmas

---

## 📝 Critérios Avaliados e Consultas

| Critério | Descrição | Pontuação | Consultas Realizadas |
|----------|-----------|-----------|------------------------|
| 1 | `SELECT` com `WHERE` | 2.0 pts | Alunos com ID > 5, Turmas com nome contendo 'Turma' |
| 2 | `GROUP BY`, `ORDER BY`, agregação | 2.0 pts | Contagem de matrículas por turma e por data |
| 3 | Operadores aritméticos | 3.0 pts | Soma e multiplicação de IDs |
| 4 | Operadores de comparação | 2.0 pts | Matrículas com data <, Turmas com ID != |
| 5 | Operadores lógicos (`AND`, `OR`) | 3.0 pts | Filtragem composta por ID e nomes |
| 6 | Operador `NOT` | 3.0 pts | Exclusão lógica em consultas |
| 7 | Operadores auxiliares (`IS NULL`, `BETWEEN`, `LIKE`, `IN`) | 3.0 pts | Busca por intervalo de datas, nomes similares, IDs específicos |
| 8 | Funções de agregação (`SUM()`, `AVG()`, etc.) | 2.0 pts | Total de matrículas, média de turmas, soma de IDs |
| 9 | Funções de data (`NOW()`, `YEAR()`, etc.) | 3.0 pts | Exibição de data atual e ano atual |
| 10 | Subconsultas | 5.0 pts | Filtragem com `IN`, `HAVING`, `UNION` |
| 11 | `JOIN` simples entre tabelas | 6.0 pts | Matrículas com aluno e turma, exibição cruzada |
| 12 | Tipos de `JOIN` (`INNER`, `LEFT`, `RIGHT`) | 6.0 pts | Testes com diferentes combinações de visualização |

✅ **Total: 40 pontos**

---

## 📂 Execução e Testes

Para executar os scripts:

1. Rode o script `CREATE DATABASE` com as tabelas  
2. Execute os `INSERT INTO` para popular com dados fictícios  
3. Teste as consultas de cada critério diretamente no cliente SQL  
4. Utilize `SELECT * FROM Matricula` ou a consulta com `JOINs` para validar os resultados

---

 
```sql
SELECT 
  m.ID_Matricula,
  a.Nome AS Aluno,
  c.Nome AS Curso,
  p.Nome AS Professor,
  t.Horario,
  t.Sala,
  m.Data_Matricula
FROM Matricula m
JOIN Aluno a ON m.Aluno_ID = a.ID_Aluno
JOIN Turma t ON m.Turma_ID = t.ID_Turma
JOIN Curso c ON t.Curso_ID = c.ID_Curso
JOIN Professor p ON t.Professor_ID = p.ID_Professor;
 

 
 
