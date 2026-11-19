---
name: configurar-agencia
description: >-
  Configura o assistente de uma agência no Travely. Use na primeira conversa,
  quando não houver perfil, quando o nome estiver vazio, ou quando a pessoa
  pedir para mudar o nome da agência, o público, o tom ou a forma do título
  do roteiro.
---

# Configurar a agência

O produto desta skill é o `perfil.md` na raiz do workspace. Não crie viagem, venda, proposta nem roteiro aqui.

Se a pessoa já pediu um ofício na mesma mensagem, termine o perfil e só então siga esse ofício.

## Antes de perguntar

`descobrir` com a frase "identidade da agência". Se `ler_identidade` voltar, use o nome, o WhatsApp e as cores como sugestão. Se a ferramenta não vier, ou a resposta for sem acesso, siga sem ela. Não chame de novo.

Consultor configura o assistente do mesmo jeito. Ele não grava a identidade da tela.

## O que perguntar

Uma mensagem só, com o que ainda estiver vazio. Não repita o que a identidade já trouxe e a pessoa não contestou.

| Campo | Pergunta | Valor |
| --- | --- | --- |
| `nome` | Como a agência aparece para o cliente? | O nome da tela, se veio. Vazio não fecha o perfil |
| `publico` | Para quem vocês vendem? | `familias`, `casais`, `corporativo`, `luxo`, `grupos` ou `misto` |
| `tom` | O texto para o cliente é próximo ou formal? | `proximo` ou `formal` |
| `titulo_roteiro` | Como começa o título do roteiro? | Um modelo com `{quem}`. Famílias e casais: `Viagem de {quem}`. Corporativo e grupos: `{destino} — {quem}`. A pessoa pode ditar outro |
| `trata_cliente` | Como chamar quem viaja no texto? | Famílias: "a família". Casais: "o casal". Corporativo: "a equipe". Grupos: "o grupo". Luxo e misto: a palavra que a pessoa escolher |
| `idioma` | Em que língua falamos e escrevemos o roteiro? | `pt` se a pessoa não disser outra |

## Gravar

Mostre o perfil numa frase. Copie o `perfil.md` desta pasta para o `perfil.md` da raiz do workspace e preencha os seis campos. Se a raiz já tem `nome`, não copie o template por cima: mude só o campo que a pessoa pediu e mantenha o resto.

O nome da tela só muda se a pessoa pedir para corrigir a identidade e `salvar_identidade` estiver no `descobrir`. Cor, WhatsApp e logo ficam na skill administrar-agencia. Público e tom não vão para a tela.
