# Validação e limites da evidência

Registro de 16/11/2026. Diferenciar quem executou evita apresentar declaração histórica como resultado novo.

## Verificações informadas por Paulo

Paulo informou que a versão em `anterior/src/solidexercicio10/` **compilou com Java 17** e que os quatro programas abaixo **passaram**. Eles têm `public static void main(String[] args)` e verificações próprias; **não são testes JUnit 5**. Os resultados foram executados pelo aluno e **não foram repetidos pelo Codex** nesta preparação.

| Programa em `anterior/tests/` | Resultado informado | Cobertura principal registrada nos fontes e em `anterior/docs/TESTES-FLUXO.md` |
| --- | --- | --- |
| `JogoServiceTest.java` | Passou, segundo Paulo | Vitória/pouso, pontuação no médio, Top 5, reset, derrotas, fim da entrada e falhas simuladas de I/O. |
| `ArquivoRankingRepositoryTest.java` | Passou, segundo Paulo | Arquivo temporário, JSON, ordenação, dados inválidos, reset e falhas de I/O. |
| `MapaRendererTest.java` | Passou, segundo Paulo | Orientação do mapa, plataforma, passageiros e ausência de mutação ao desenhar. |
| `SolidPauloTest.java` | Passou, segundo Paulo | Catálogo extensível, passageiro novo, geração sem sobreposição e capacidade. |

O resultado de 82 pontos no teste de fluxo é do modo **médio**; não resolve a diferença inicial no difícil. Os quatro programas não verificam desembarque, contagem de entregues, independência arquitetural exigida na Fase 1 nem a interpretação da perda de pontos em colisão. Passarem não prova esses requisitos.

## Comandos de verificação executados pelo Codex nesta preparação

Os comandos abaixo foram executados no terminal do workspace em 16/11/2026. Para os comandos Git, a opção `-c safe.directory=...` foi usada **somente na invocação**, pois o sandbox tem proprietário diferente; não houve alteração da configuração global.

| Comando executado | Resultado observado |
| --- | --- |
| `$env:JAVA_HOME`; `java -version`; `javac -version` | `JAVA_HOME` apontou para `C:\Program Files\Eclipse Adoptium\jdk-17.0.21.9-hotspot`; Java e javac informaram **17.0.21**. |
| `git -c safe.directory='C:/Users/Paulo edvandro rocha/Projetos/missao-marte-preparacao/anterior' -C anterior rev-parse HEAD` | `0e4304f86e0adce6a788925ecc2f5b5aaf68de24`. |
| `git -c safe.directory='C:/Users/Paulo edvandro rocha/Projetos/missao-marte-preparacao/entrega' -C entrega rev-parse HEAD` | `23157660e75eed329424a353741f808d71bcebb8` antes do commit desta preparação. |
| `git -c safe.directory='C:/Users/Paulo edvandro rocha/Projetos/missao-marte-preparacao/entrega' -C entrega remote get-url origin` | `https://github.com/paulo-edvandro/missao-marte-unifor.git`, exatamente a URL indicada para este trabalho. |
| `git -c safe.directory='C:/Users/Paulo edvandro rocha/Projetos/missao-marte-preparacao/anterior' -C anterior status --short --untracked-files=all` | Sem saída: entrega anterior limpa. |
| `git -c safe.directory='C:/Users/Paulo edvandro rocha/Projetos/missao-marte-preparacao/entrega' -C entrega diff --check` | Código de saída **0**, sem erro de whitespace no diff dos arquivos já rastreados. |
| `git -c safe.directory='C:/Users/Paulo edvandro rocha/Projetos/missao-marte-preparacao/entrega' -C entrega status --short --untracked-files=all` | `README.md` modificado; `.gitignore` e quatro documentos novos não rastreados, antes de adicioná-los ao commit. |

Com `git ... -C entrega check-ignore -q --no-index -- <caminho>`, foram testados caminhos de exemplo das fases: `build/classes/Main.class`, `.gradle/cache.bin`, `ranking.json`, `data.mv.db`, `local.properties` e `.env` foram **ignorados**; `gradlew`, `gradlew.bat`, `gradle/wrapper/gradle-wrapper.jar`, `gradle/wrapper/gradle-wrapper.properties`, `.env.example` e `application-example.yml` foram **permitidos**. A opção `--no-index` permite consultar esses caminhos sem criar as futuras pastas.

Pelo conector GitHub, foi consultada a branch oficial `main` e obtido `d16cdaad47f0a5aad6a133fea2444bd91417801d`; foram lidos nesse commit os trechos de pontuação da Fase 0 e requisitos da Fase 1. Essa consulta não executou o projeto oficial. A branch remota `main` de `paulo-edvandro/missao-marte-unifor` também foi consultada pelo conector antes do commit documental e apontava para `23157660e75eed329424a353741f808d71bcebb8`, igual ao HEAD local. `git ls-remote origin refs/heads/main` falhou por falta de conexão deste terminal com `github.com:443`; isso não foi tratado como diferença remota.

## Ainda não verificado

- Compilação ou execução de jogo em `entrega/`: não há código de jogo aqui.
- Nova execução dos quatro programas: esta etapa é apenas documental.
- Gradle, libGDX, API Spring Boot e Android: não há projetos dessas fases em `entrega/`.
- Resultado de regras divergentes em nova implementação: dependem das decisões em [decisoes.md](decisoes.md).

Cada fase futura deverá registrar **comandos realmente executados, ambiente, resultado e limitações** antes de ser marcada como validada. Os programas com `main` podem inspirar cenários; a Fase 2 requer testes próprios em JUnit 5 pelo Gradle.
