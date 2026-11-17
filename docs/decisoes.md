# Requisitos, observações, propostas e decisões pendentes

Registro de 16/11/2026. **Requisito explícito** vem das orientações; **comportamento observado** descreve código ou documentos consultados; **proposta da equipe** é opção para discussão, ainda sem aprovação de regra; **decisão pendente** requer escolha registrada antes de alterar o jogo. Nenhuma decisão abaixo declara aprovação do professor.

Fontes fixas: [AVA](https://github.com/marcelobezerra-dotcom/T200-ProjArqSist/blob/d16cdaad47f0a5aad6a133fea2444bd91417801d/missaoMarteUnifor/projetoExtensaoFinal/ENUNCIADO_AVA.md), [PROMPT_MESTRE](https://github.com/marcelobezerra-dotcom/T200-ProjArqSist/blob/d16cdaad47f0a5aad6a133fea2444bd91417801d/missaoMarteUnifor/projetoExtensaoFinal/PROMPT_MESTRE.md), [Fase 0](https://github.com/marcelobezerra-dotcom/T200-ProjArqSist/tree/d16cdaad47f0a5aad6a133fea2444bd91417801d/missaoMarteUnifor/projetoExtensaoFinal/exercicio10/fases/fase-0-oopuro), [enunciado da Fase 1](https://github.com/marcelobezerra-dotcom/T200-ProjArqSist/blob/d16cdaad47f0a5aad6a133fea2444bd91417801d/missaoMarteUnifor/projetoExtensaoFinal/exercicio10/fases/fase-01-refatoracao/docs/fase-01-enunciado.md) e [enunciado da Fase 2](https://github.com/marcelobezerra-dotcom/T200-ProjArqSist/blob/d16cdaad47f0a5aad6a133fea2444bd91417801d/missaoMarteUnifor/projetoExtensaoFinal/exercicio10/fases/fase-02-gradle/docs/fase-02-enunciado.md). Os caminhos `anterior/...` são relativos ao workspace, fora deste repositório.

## Base e regras de jogo

| Tipo | Registro e evidência |
| --- | --- |
| **Requisito explícito** | Preservar a versão de entrada e manter fases independentes; documentar mudanças de comportamento (PROMPT_MESTRE e Fase 1). |
| **Comportamento observado** | `anterior/src/exercicio10/Main.java:232-237` e `anterior/src/solidexercicio10/service/JogoService.java:111-116` iniciam o difícil com **15** pontos. `fase-0-oopuro/src/Main.java:244-249` oficial inicia com **45**. Fácil e médio são 30 e 20 nas versões examinadas. |
| **Decisão pendente** | Qual pontuação inicial do difícil regerá a evolução? Registrar origem, motivo e impacto nos testes; nenhum dos valores foi aprovado nesta etapa. |
| **Comportamento observado** | Fase 0 oficial e `anterior/src/solidexercicio10/service/JogoService.java:176-185` vencem com todos embarcados e a nave em `(0,0)`. |
| **Requisito explícito** | A Fase 1 pede **desembarque ao chegar à base**, liberação da capacidade, **contagem de entregues** e vitória somente após entregar todos. Os indicadores devem satisfazer `a bordo + entregues + restantes no mapa = total`. |
| **Decisão pendente** | Registrar a transição intencional entre a vitória da Fase 0 e a regra da Fase 1, inclusive o retorno à base antes do último resgate. A versão anterior não é automaticamente conforme. |
| **Comportamento observado** | Na Fase 0 e em `anterior/src/solidexercicio10/service/JogoService.java:153-174`, o movimento custa 1 ponto e a colisão tira vida; não há desconto adicional explícito pela colisão. |
| **Requisito explícito** | O roteiro da Fase 1 pede verificar perda de vida **e de pontos** após colisão. |
| **Decisão pendente** | Esclarecer se a perda pelo movimento que levou à colisão satisfaz o roteiro ou se há penalidade adicional. **Nenhum valor adicional foi definido.** |
| **Comportamento observado** | A versão SOLID limita o alcance do mapa a 2–50 (`JogoService.java:98-109`); a Fase 0 oficial aceita todo inteiro positivo. Os símbolos e a legenda também diferem (`MapaRenderer.java:40-81`). |
| **Proposta da equipe para discussão** | Manter uma tabela de diferenças observáveis por fase e validá-las no console antes de transportar regras para libGDX. A equipe ainda escolherá o que preservar ou corrigir. |

## Arquitetura e build

| Tipo | Registro e evidência |
| --- | --- |
| **Requisito explícito** | Na Fase 1, `domain` e `application` **não importam** `console` nem `infrastructure`; `Main` monta dependências; comandos viram **ações tipadas** antes das regras; criação de missão fica isolada; ranking usa interface substituível (enunciado da Fase 1, seções 4.1–4.2). |
| **Comportamento observado** | A versão anterior separa `model`, `service`, `presentation` e `repository`, mas `JogoService` importa `JogoConsole`, `MapaRenderer` e `RankingEntry`, lê `Scanner` e interpreta `char` (`anterior/src/solidexercicio10/service/JogoService.java:9-18,38-58,129-160`). Não satisfaz integralmente a dependência exigida. |
| **Proposta da equipe para discussão** | No plano próprio da Fase 1, mapear responsabilidades anteriores para domínio, aplicação e adaptadores, criando apenas as abstrações necessárias e preservando o console. Nenhuma classe foi criada agora. |
| **Requisito explícito** | Fase 2: JDK 17, Gradle Wrapper versionado, projeto executável, UTF-8 e testes **JUnit 5** pelo Gradle, preservando o comportamento da Fase 1. |
| **Comportamento observado** | Os quatro testes de `anterior/tests/` são programas Java com `main`. A versão anterior não tem projeto Gradle; mover esses programas não os transforma em JUnit. |
| **Decisão pendente** | Planejar a Fase 2 após validar a Fase 1; conferir no ambiente real as versões e comandos antes de fixá-los. |

## Reaproveitamento: duas interpretações

1. **Evoluir o código de entrada do professor preservado na entrega anterior.** A entrada seria `anterior/src/exercicio10/`, que guarda esse código de entrada. A refatoração em `anterior/src/solidexercicio10/` foi desenvolvida pela equipe e é uma contribuição histórica distinta, útil para estudar decisões e testes; não deve ser confundida com a entrada original nem adotada silenciosamente como solução da Fase 1 atual. A Fase 0 oficial serviria para comparar requisitos. Esta interpretação preserva o percurso anterior, mas exige resolver diferenças como **15/45** e demonstrar a evolução pedida.
2. **Usar a Fase 0 oficial como código de entrada fornecido.** O PROMPT_MESTRE descreve partir de cópia do projeto inicial para a Fase 1, preservando a origem. O AVA diz estudar o código existente e **não copiar código**. Uma interpretação é que a proibição alcance soluções prontas das fases seguintes e não o código de entrada; outra é que também alcance a Fase 0. **Nenhuma foi confirmada.**

**Dúvida específica a esclarecer:** a equipe deve partir do código de entrada do professor preservado em `anterior/src/exercicio10/` ou da Fase 0 oficial? A orientação “não copie o código” permite incluir a **base de entrada fornecida** como fase preservada, desde que não se copiem **soluções prontas** das fases 1–7? Até a resposta, não copiar Java nem criar a pasta da Fase 0.

## Divergência futura

O PROMPT_MESTRE da Fase 5 diz que login é obrigatório para jogar; o AVA pede preservar modo convidado e ranking local. Resolver no plano da Fase 5. Nenhuma regra de autenticação foi escolhida ou implementada agora.
