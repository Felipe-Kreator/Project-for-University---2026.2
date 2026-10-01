# Documentação do Projeto — CyberQuiz

**Projeto:** CyberQuiz — Quiz de Cibersegurança  
**Disciplina:** Projeto Universitário  
**Período:** 2026.2  
**Integrantes:** João, Maria e Felipe  
**Tecnologias previstas:** HTML5, CSS3, JavaScript e PostgreSQL

## 1. Introdução

O CyberQuiz é uma aplicação web educacional destinada a testar e ampliar os conhecimentos dos usuários sobre cibersegurança por meio de perguntas interativas.

A aplicação abordará conceitos de segurança digital, boas práticas de proteção de dados, ameaças cibernéticas e prevenção de ataques. O sistema deverá permitir que os participantes respondam a perguntas, acompanhem seu desempenho e consultem um ranking.

## 2. Objetivos

### 2.1 Objetivo geral

Desenvolver uma aplicação web de quiz sobre cibersegurança que incentive o aprendizado e permita avaliar os conhecimentos dos participantes de forma interativa.

### 2.2 Objetivos específicos

- Desenvolver uma interface intuitiva e acessível.
- Apresentar perguntas sobre diferentes tópicos de cibersegurança.
- Implementar respostas e cálculo de pontuação.
- Armazenar perguntas e resultados.
- Disponibilizar um ranking.
- Separar as responsabilidades do frontend, backend e banco de dados.
- Aplicar boas práticas de segurança durante o desenvolvimento.

## 3. Justificativa

A cibersegurança é relevante diante do crescimento das ameaças digitais e da utilização cotidiana de sistemas conectados. O quiz propõe uma forma interativa de abordar temas como senhas, phishing, proteção de dados e segurança na internet.

O projeto também permite aplicar conhecimentos de desenvolvimento web, lógica de programação, banco de dados, integração de sistemas e segurança da informação.

## 4. Escopo

### 4.1 Funcionalidades previstas

- Tela inicial com apresentação do projeto.
- Início de partidas.
- Exibição de perguntas de múltipla escolha.
- Seleção de alternativas.
- Validação das respostas.
- Cálculo e apresentação da pontuação.
- Registro de resultados.
- Consulta ao ranking.
- Organização de perguntas por categorias ou níveis, conforme decisão da equipe.

### 4.2 Fora do escopo inicial

- Aplicativo nativo para dispositivos móveis.
- Autenticação avançada.
- Geração automática de perguntas por inteligência artificial.
- Multijogador em tempo real.
- Integração com plataformas externas de ensino.
- Painel administrativo avançado.

Esses itens poderão ser avaliados em versões futuras.

## 5. Tecnologias

| Tecnologia | Finalidade |
|---|---|
| HTML5 | Estrutura das páginas |
| CSS3 | Estilização e responsividade |
| JavaScript | Lógica do frontend e backend |
| PostgreSQL | Persistência dos dados |
| Git | Controle de versão |
| GitHub | Colaboração e hospedagem |

O ambiente de execução do backend precisa ser confirmado. JavaScript no navegador não substitui um ambiente de servidor. Node.js é uma possibilidade, mas seu uso deve respeitar as regras da disciplina.

## 6. Arquitetura

A aplicação será organizada em três componentes:

- **Frontend:** apresenta as telas, recebe as interações e comunica-se com o backend.
- **Backend:** disponibiliza operações, consulta perguntas, valida respostas, calcula pontuações e registra resultados.
- **Banco de dados:** armazena perguntas, alternativas, participantes e partidas.

### Fluxo principal

1. O usuário acessa a aplicação.
2. O frontend solicita perguntas ao backend.
3. O backend consulta o banco de dados.
4. As perguntas são apresentadas ao usuário.
5. O usuário envia suas respostas.
6. O backend valida as respostas e calcula a pontuação.
7. O resultado é registrado.
8. O frontend apresenta o resultado e permite consultar o ranking.

## 7. Segurança

A aplicação deverá considerar que os dados enviados pelo frontend podem ser manipulados. A validação da resposta e o cálculo da pontuação devem ocorrer no backend.

Medidas previstas:

- Validar entradas recebidas pelo backend.
- Utilizar consultas parametrizadas para reduzir o risco de SQL Injection.
- Não enviar a resposta correta antes do momento adequado.
- Não armazenar segredos diretamente no código-fonte.
- Retornar apenas as informações necessárias ao frontend.
- Tratar erros sem expor detalhes internos.
- Proteger o acesso ao banco de dados.
- Utilizar HTTPS em ambientes publicados na internet.

## 8. Testes previstos

- Exibição de perguntas e alternativas.
- Seleção de respostas.
- Validação de respostas corretas e incorretas.
- Cálculo da pontuação.
- Registro e consulta de resultados.
- Ordenação do ranking.
- Tratamento de entradas inválidas.
- Comunicação entre frontend, backend e banco de dados.
- Verificação de que respostas corretas não são expostas antecipadamente.

## 9. Resultados esperados

Espera-se entregar uma aplicação funcional que permita testar conhecimentos sobre cibersegurança, visualizar resultados e consultar um ranking. O projeto também deverá demonstrar a aplicação prática de conceitos de programação, banco de dados, integração e desenvolvimento seguro.

## 10. Considerações finais

Esta documentação descreve a proposta inicial do CyberQuiz. Ela deverá ser atualizada ao longo do desenvolvimento para refletir os requisitos confirmados, as decisões técnicas e as funcionalidades efetivamente implementadas.
