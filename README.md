# Missão Marte — Evolução Arquitetural

Repositório acadêmico da equipe **Lucas, Emerson e Paulo**. O jogo Java de console será evoluído por fases, até cliente gráfico, Android e servidor independente. **Neste momento, `entrega/` contém somente preparação documental**: ainda não há aplicação, Gradle Wrapper, testes ou comandos de build neste repositório.

## Documentos

- [Origem e contribuições](docs/origem-e-contribuicoes.md): repositórios, commits, caminhos consultados e autoria histórica.
- [Decisões](docs/decisoes.md): requisitos, comportamento observado, propostas e dúvidas abertas.
- [Validação](docs/validacao.md): evidências informadas pelo aluno e verificações desta etapa.
- [Plano de trabalho](docs/plano-de-trabalho.md): responsabilidades, estrutura futura e checkpoints.

## Ambiente

O trabalho exige **JDK 17**. Em 16/11/2026, neste terminal, `JAVA_HOME`, `java -version` e `javac -version` indicaram Temurin 17.0.21. A máquina também tem Java 25; cada terminal e build futuro precisará confirmar a JVM efetiva. A presença do JDK 17 não valida um build que ainda não existe em `entrega/`.

## Fontes e responsabilidades

A entrega anterior está em `../anterior/` apenas no workspace local. A [fonte oficial](https://github.com/marcelobezerra-dotcom/T200-ProjArqSist/tree/d16cdaad47f0a5aad6a133fea2444bd91417801d/missaoMarteUnifor/projetoExtensaoFinal) foi consultada como referência. A base da Fase 0 e as regras divergentes aguardam decisão em [decisoes.md](docs/decisoes.md).

**Lucas** conduz arquitetura, regras do jogo, Gradle e regra da melhoria final. **Emerson** conduz libGDX, interface e Android. **Paulo** conduz servidor Spring Boot e integração, participa das decisões arquiteturais e coordena esta preparação. Autoria da entrega anterior e trabalho novo são registrados separadamente.

Nenhuma pasta de fase foi criada. Cada fase futura terá instruções e evidências próprias quando for autorizada e realizada.
