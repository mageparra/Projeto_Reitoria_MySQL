<<!DOCTYPE html>
<html>
<head>

</head>
<body>
  <h1>Principais Scripts do Projeto Reitoria 📔 </h1>
  <p>Aqui estão os principais scripts para buscar informações no Projeto Reitoria:</p>

  <h3>Consulta para listar o quantitativo de cursos existentes:</h3>
  <pre>
    <code>select count(IdCurso) as CursosExistentes from Curso;</code>
  </pre>

  <h3>Consulta para listar o nome das disciplinas existentes:</h3>
  <pre>
    <code>select nome from Disciplina;</code>
  </pre>

  <h3>Consulta para listar o nome de todos os cursos e o nome de seus respectivos alunos, em ordem decrescente, pelo nome dos cursos:</h3>
  <pre>
    SELECT Curso.nome AS NomeDoCurso, Aluno.nome AS NomeDoAluno
    FROM Curso
    INNER JOIN AlunoCurso ON Curso.IdCurso = AlunoCurso.IdCurso
    INNER JOIN Aluno ON AlunoCurso.IdAluno = Aluno.IdAluno
    ORDER BY Curso.nome DESC, Aluno.nome;
  </pre>

  <h3>Consulta para listar o nome das disciplinas e a média das notas das disciplinas em todos os cursos utilizando o comando group by:</h3>
  <pre>
   SELECT Disciplina.nome AS NomeDaDisciplina, AVG(Historico.nota) AS MediaDasNotas
   FROM Disciplina
   INNER JOIN Historico ON Disciplina.IdDisciplina = Historico.IdDisciplina
   GROUP BY Disciplina.nome;</code>
  </pre>

  <h3>Consulta para listar o nome de todos os cursos e a quantidade de alunos em cada curso utilizando os comandos join e group by:</h3>
  <pre>
    <code>SELECT Curso.nome AS NomeDoCurso, COUNT(AlunoCurso.IdAluno) AS QuantidadeDeAlunos
    FROM Curso
    LEFT JOIN AlunoCurso ON Curso.IdCurso = AlunoCurso.IdCurso
    GROUP BY Curso.nome;</code>
  </pre>


</body>
</html>
