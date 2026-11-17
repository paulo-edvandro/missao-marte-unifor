# Plano de trabalho e estrutura proposta

Este documento organiza trabalho futuro; **não declara fases concluídas**. As pastas abaixo são uma proposta e **não foram criadas** nesta preparação. A fonte oficial pede versões independentes; a Fase 5 terá cliente e servidor separados.

```text
entrega/
├── README.md, .gitignore, docs/             # preparação atual
└── exercicio10/
    └── fases/
        ├── fase-0-oopuro/                  # base a definir; preservar
        ├── fase-01-refatoracao/            # console e arquitetura
        ├── fase-02-gradle/                 # build e JUnit 5
        ├── fase-03-libgdx/                 # cliente gráfico inicial
        ├── fase-04-interface-grafica/      # interface jogável
        ├── fase-05-servidor-ranking/
        │   ├── cliente/                    # projeto cliente
        │   └── servidor/                   # Spring Boot independente
        ├── fase-06-android/                # plataforma móvel
        └── fase-07-evolucao-livre/         # melhoria da equipe
```

Cada fase só ganha pasta após autorização própria. Quando houver aplicação, deverá conter fontes, build, testes, README e `docs/fase-XX-tutorial.md` pertinentes. Nas fases Gradle, versionar `gradlew`, `gradlew.bat`, `gradle/wrapper/gradle-wrapper.properties` **e** `gradle/wrapper/gradle-wrapper.jar`; saídas de build ficam fora do Git. Na Fase 5, cliente e servidor terão builds e instruções separados. O servidor não dependerá do código do cliente.

## Divisão de trabalho

| Integrante | Condução nesta atividade | Evidência a registrar quando ocorrer |
| --- | --- | --- |
| Lucas | Arquitetura, regras do jogo, Gradle e regra da melhoria final. | Decisões de domínio, mudanças de regra, build, testes e revisões. |
| Emerson | libGDX, interface gráfica e Android. | Cliente gráfico/móvel, testes, execução e limitações de ambiente. |
| Paulo | Servidor Spring Boot e integração; preparação e decisões arquiteturais conjuntas. | Contrato da API, persistência/autenticação, integração, testes e decisões. |

A divisão permite revisão cruzada e ajustes combinados. Responsabilidade planejada não substitui autoria demonstrada em commits, PRs e documentos. A autoria anterior está em [origem-e-contribuicoes.md](origem-e-contribuicoes.md).

## Checkpoints pequenos e verificáveis

1. **Preparação documental — agora:** revisar estes documentos, conferir origem, `.gitignore`, diff e status; registrar e enviar somente a documentação autorizada. Sem código ou implementação.
2. **Entrada e Fase 0:** esclarecer a base a preservar e divergências em [decisoes.md](decisoes.md). Só então criar a pasta aprovada e verificar proveniência/integridade.
3. **Fase 1 — plano específico:** Lucas conduz regras/arquitetura com Paulo. Mapear responsabilidades, ações tipadas, desembarque, entregues, contagem e dependências permitidas. Definir testes e efeitos no console; implementar só após aprovação dessa fase.
4. **Fase 2 — plano específico:** Lucas conduz Gradle. Confirmar JDK 17 e Wrapper; migrar a Fase 1 preservando fontes/comportamento, criar JUnit 5 e registrar comandos/resultados. Sem antecipar libGDX.
5. **Fases 3 e 4 — planos próprios:** Emerson conduz libGDX e interface, mantendo regras fora das telas. Verificar desktop e domínio sem janela.
6. **Fase 5 — plano próprio:** Paulo pode preparar o contrato da API. Mediante plano e autorização próprios da Fase 5, poderá desenvolver e testar o servidor Spring Boot isoladamente, em paralelo à evolução do cliente. Isso não conclui a Fase 5: a integração e seus testes dependem de um cliente disponível. O plano também deverá resolver a divergência login/convidado e prever comunicação sem bloquear a interface.
7. **Fases 6 e 7 — planos próprios:** Emerson conduz Android; Lucas conduz a regra da melhoria final. Registrar testes, limitações e preservação do desktop.

O [AVA](https://github.com/marcelobezerra-dotcom/T200-ProjArqSist/blob/d16cdaad47f0a5aad6a133fea2444bd91417801d/missaoMarteUnifor/projetoExtensaoFinal/ENUNCIADO_AVA.md) situa 16–22/11/2026 na Sprint 3. O estágio documental real deste repositório está anterior a essas entregas; quadro e relatório futuros devem refletir essa diferença sem marcar trabalho não realizado como concluído.
