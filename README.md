# Desafio de Modelagem Dimensional (Star Schema) 🌟

## Objetivo do Projeto
O objetivo deste desafio foi converter um diagrama Entidade-Relacionamento (Relacional) de um ambiente acadêmico (Universidade) em um **Diagrama Dimensional (Star Schema)**, utilizando o Power BI. 

Seguindo as regras de negócio do desafio, o foco do modelo é a **análise da atuação dos Professores**, ignorando os dados de alunos e matrículas. 

## Arquitetura do Modelo (Star Schema)
Para resolver o problema, foi criada uma base de dados analítica (mock data) diretamente no Power BI, estruturada da seguinte forma:

### 🎯 Tabela Fato (`Fato_Professor`)
Representa o evento central da análise: a atribuição de aulas de um professor.
- **Métrica criada:** `Carga_Horaria` (horas lecionadas).
- **Chaves Estrangeiras (FKs):** `idProfessor`, `idDepartamento`, `idCurso`, `idDisciplina`, `idData`.

### 🧩 Tabelas Dimensão
Fornecem o contexto descritivo para a tabela fato:
1. **`Dim_Professor`:** Detalhes do objeto de análise (Ex: Nome do Professor).
2. **`Dim_Departamento`:** Contexto organizacional (Ex: Nome do Departamento, Campus).
3. **`Dim_Curso`:** Contexto acadêmico macro.
4. **`Dim_Disciplina`:** Detalhes da matéria lecionada.
5. **`Dim_Data`:** Dimensão criada especificamente para suprir a ausência de datas no modelo relacional original, permitindo analisar a oferta de disciplinas por Ano e Semestre.

## Justificativa da Modelagem
A abordagem em estrela centraliza os IDs na Tabela Fato, permitindo que a universidade cruze informações rapidamente: "Quantas horas o Professor X lecionou no Curso Y durante o Semestre Z?". Alunos e tabelas ponte (como a associação N:N entre disciplinas e pré-requisitos) foram deliberadamente descartados para manter a performance e o foco analítico exigido pelo escopo da tarefa.

## Como acessar
Baixe o arquivo `.pbix` contido neste repositório e acesse a aba "Exibição de Modelo" para visualizar o Star Schema construído.
