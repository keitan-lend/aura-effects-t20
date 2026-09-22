# Aura Effects — Fork de compatibilidade com Tormenta20

Este repositório é um fork do módulo original **[Aura Effects](https://git.gay/roth-michael/Aura-Effects)**, de Michael Roth (roth-michael), com ajustes para funcionar de forma totalmente compatível com o sistema **Tormenta20** no **Foundry VTT v14**.

Toda a documentação de uso, exemplos e explicação dos campos permanece no repositório original — aqui constam apenas as alterações feitas nesta versão.

## Alterações desta versão (2.2.2-t20.1)

- **Correção de bug em `queries.mjs`**: na escolha de qual aura "vence" entre múltiplos efeitos não-empilháveis com o mesmo nome, a comparação usava o documento original (`effect`) em vez dos dados já processados (`effectData`), fazendo a substituição nunca (ou incorretamente) acontecer.
- **Novo hook `updateItem`**: no Tormenta20 (assim como no dnd5e), a supressão de efeitos por equipamento é controlada por um campo do *Item* (`system.equipado`), não pelo próprio Active Effect. Sem esse hook, equipar/desequipar um item que carrega uma aura não atualizava a região automaticamente.
- **Tradução pt-BR completada**: adicionadas as 4 chaves que faltavam em `lang/pt-BR.json` (`collisionType` e `HighlightMode`).
- **Compatibilidade de schema verificada**: confirmado, por leitura de código, que a detecção automática em `registerAuraType()`/`registerAuraSheet()` mistura corretamente com o `BaseEffect` e a sheet `ActiveEffectConfigT20` do Tormenta20, sem colisão de nomes de campo entre os campos do módulo e os campos próprios do sistema (`targets`, `status`, `onuse`, `abilityUse`, `aura`).

Detalhes completos no [CHANGELOG.md](CHANGELOG.md).

## Licença

MIT, herdada do projeto original — ver [LICENSE](LICENSE).
