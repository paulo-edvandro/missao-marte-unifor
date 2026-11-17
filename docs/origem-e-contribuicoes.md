# Origem, versões consultadas e contribuições

Registro de 16/11/2026. Um **commit consultado** identifica a versão examinada; não comprova autoria de cada linha nem conclusão de fase.

| Fonte | Repositório e commit | Caminhos consultados |
| --- | --- | --- |
| Entrega anterior, cópia local `../anterior/` | [`paulo-edvandro/projeto_marte_missao`](https://github.com/paulo-edvandro/projeto_marte_missao), `main` em [`0e4304f86e0adce6a788925ecc2f5b5aaf68de24`](https://github.com/paulo-edvandro/projeto_marte_missao/commit/0e4304f86e0adce6a788925ecc2f5b5aaf68de24) | `README.md`, `REVISAO-SOLID.md`, `src/exercicio10/`, `src/solidexercicio10/`, `tests/`, `docs/CONTRATOS.md`, `docs/TESTES-FLUXO.md`, `docs/TESTES-MODELO.md`, `docs/uml/`. |
| Trabalho atual, cópia local `../entrega/` | [`paulo-edvandro/missao-marte-unifor`](https://github.com/paulo-edvandro/missao-marte-unifor), `main` inicialmente em [`23157660e75eed329424a353741f808d71bcebb8`](https://github.com/paulo-edvandro/missao-marte-unifor/commit/23157660e75eed329424a353741f808d71bcebb8) | `README.md` inicial, status e `origin`. Os documentos desta preparação foram produzidos depois desse commit inicial. |
| Fonte oficial | [`marcelobezerra-dotcom/T200-ProjArqSist`](https://github.com/marcelobezerra-dotcom/T200-ProjArqSist), `main` em [`d16cdaad47f0a5aad6a133fea2444bd91417801d`](https://github.com/marcelobezerra-dotcom/T200-ProjArqSist/commit/d16cdaad47f0a5aad6a133fea2444bd91417801d) | `missaoMarteUnifor/projetoExtensaoFinal/ENUNCIADO_AVA.md`, `PROMPT_MESTRE.md`, `README.md`; `exercicio10/fases/fase-0-oopuro/src/` (README, Main e modelo); enunciado, planejamento e README das Fases 1 e 2. |

Os dois commits locais foram obtidos com `git rev-parse HEAD`; o oficial, da branch `main` consultada no GitHub. As soluções oficiais das fases seguintes não foram adotadas como implementação. A `main` remota de `entrega/` foi consultada antes do commit documental e apontava para `23157660e75eed329424a353741f808d71bcebb8`. **Não foi verificado** o estado remoto atual de `anterior/`.

## Autoria histórica

O [README anterior](https://github.com/paulo-edvandro/projeto_marte_missao/blob/0e4304f86e0adce6a788925ecc2f5b5aaf68de24/README.md) e `REVISAO-SOLID.md` atribuem:

| Integrante | Trabalho registrado na entrega anterior |
| --- | --- |
| Lucas Alencar (`luken6406`) | Entidades e regras do modelo; diagrama de classes. |
| Emerson (`EmsRibeiro`) | Ranking JSON, renderização do mapa e diagrama de pacotes. |
| Paulo Edvandro Rocha Filho (`paulo-edvandro`) | Fluxo da partida, ponto de entrada, integração, testes do fluxo e documentação. |

O README anterior cita o [repositório compartilhado histórico](https://github.com/paulo-edvandro/missao-marte-solid). Seu histórico remoto **não foi consultado nesta etapa**. A revisão anterior menciona o commit `4b5153b63feade9e2a3328121c860b1fd7bd4bd6` e PR #7; esses identificadores foram lidos no documento, não auditados agora. Não são prova de autoria individual de cada linha.

## Trabalho novo

| Integrante | Responsabilidade planejada nesta atividade |
| --- | --- |
| Lucas | Conduz arquitetura, regras do jogo, Gradle e regra da melhoria final. |
| Emerson | Conduz libGDX, interface gráfica e Android. |
| Paulo | Conduz servidor Spring Boot e integração; coordena a preparação e participa das decisões arquiteturais. |

A divisão descreve trabalho **planejado**, não entrega concluída. Em cada fase, registrar autores, revisores, decisões e testes no histórico real. Alterações de integração em arquivos iniciados por outro integrante devem preservar o crédito histórico e identificar quem fez a mudança nova. IA auxiliou na análise e redação desta preparação; a equipe deve revisar e conseguir explicar o conteúdo.
