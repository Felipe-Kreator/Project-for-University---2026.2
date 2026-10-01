# Modelagem do Banco de Dados — CyberQuiz

## 1. Objetivo

Este documento apresenta uma proposta inicial para armazenar perguntas, alternativas, participantes, partidas e pontuações no PostgreSQL.

O modelo deverá ser revisado após a definição das regras de negócio.

## 2. Entidades

### 2.1 participantes

| Campo | Tipo sugerido | Restrições | Descrição |
|---|---|---|---|
| id | INTEGER | PK | Identificador |
| nome | VARCHAR(100) | NOT NULL | Nome ou apelido |
| criado_em | TIMESTAMP | NOT NULL | Data de criação |

### 2.2 categorias

| Campo | Tipo sugerido | Restrições | Descrição |
|---|---|---|---|
| id | INTEGER | PK | Identificador |
| nome | VARCHAR(100) | NOT NULL | Nome da categoria |
| descricao | TEXT | — | Descrição |

### 2.3 perguntas

| Campo | Tipo sugerido | Restrições | Descrição |
|---|---|---|---|
| id | INTEGER | PK | Identificador |
| categoria_id | INTEGER | FK | Categoria relacionada |
| enunciado | TEXT | NOT NULL | Texto da pergunta |
| dificuldade | VARCHAR(20) | — | Nível de dificuldade |
| explicacao | TEXT | — | Explicação da resposta |

### 2.4 alternativas

| Campo | Tipo sugerido | Restrições | Descrição |
|---|---|---|---|
| id | INTEGER | PK | Identificador |
| pergunta_id | INTEGER | FK | Pergunta relacionada |
| texto | TEXT | NOT NULL | Texto da alternativa |
| correta | BOOLEAN | NOT NULL | Indica a alternativa correta |

### 2.5 partidas

| Campo | Tipo sugerido | Restrições | Descrição |
|---|---|---|---|
| id | INTEGER | PK | Identificador |
| participante_id | INTEGER | FK | Participante |
| pontuacao | INTEGER | NOT NULL | Pontuação final |
| total_perguntas | INTEGER | NOT NULL | Total de perguntas |
| iniciada_em | TIMESTAMP | NOT NULL | Início |
| finalizada_em | TIMESTAMP | — | Conclusão |

## 3. Relacionamentos

- Uma categoria pode possuir várias perguntas.
- Cada pergunta pertence a uma categoria, caso a categorização seja obrigatória.
- Uma pergunta possui várias alternativas.
- Cada alternativa pertence a uma pergunta.
- Um participante pode realizar várias partidas.
- Cada partida pertence a um participante, caso seja exigida identificação.

## 4. Regras de integridade

- Cada entidade deve possuir uma chave primária.
- As referências devem utilizar chaves estrangeiras.
- Perguntas e alternativas não devem ficar sem os vínculos necessários.
- A pontuação e a quantidade de perguntas devem ser valores válidos e não negativos.
- A regra de quantidade de alternativas corretas por pergunta deve ser garantida pela aplicação ou por restrições adequadas.

## 5. Segurança

A aplicação não deve retornar o campo que identifica a alternativa correta junto com as perguntas antes da validação. O backend deve controlar a correção e a pontuação.

Consultas SQL devem ser parametrizadas. O usuário de banco utilizado pela aplicação deve possuir somente as permissões necessárias.

## 6. Decisões pendentes

- Se participantes poderão jogar sem cadastro.
- Se o nome será único.
- Se será necessário registrar cada resposta individual.
- Como será calculado o ranking.
- Se haverá histórico detalhado de partidas.
- Se perguntas poderão ter mais de uma alternativa correta.
