---
name: administrar-agencia
description: >-
  Administra usuários, chave MCP, meta, custo, fechamento, identidade e
  portfólio no Travely. Use quando a pessoa pedir para criar usuário, emitir
  ou revogar chave, gravar meta, lançar ou apagar custo, mudar o dia do
  fechamento, mudar nome ou cor da agência, ou publicar no portfólio. Pare se
  descobrir não devolver a ferramenta.
---

# Administrar a agência

Leia `perfil.md` na raiz. Sem arquivo, ou com `nome` vazio, pare e siga configurar-agencia.

Comece com `descobrir` da frase da pessoa. Lista vazia ou sem acesso: pare. Não repita a chamada com outro nome. Grave com `executar_gravacao`.

| Pedido | Ferramenta | Confirmação |
| --- | --- | --- |
| Quem entra no sistema | `listar_usuarios` | Leitura. Sem senha e sem o segredo |
| Criar ou mudar cargo, gerente, ativo | `salvar_usuario` | A senha temporária volta uma vez, na criação. A própria conta não muda cargo nem ativo |
| Outra senha temporária | `senha_temporaria` | Não é a própria conta. O valor se mostra uma vez |
| Chave do assistente | `chave_mcp` | `emitir`, `renovar` ou `revogar`. Revogar pede `confirmar=true`. O segredo volta uma vez |
| Apagar quem não tem livro | `apagar_usuario` | `confirmar=true`. Quem já tem viagem, venda, proposta ou cliente perde o acesso com ativo falso |
| Meta de comissão | `salvar_meta` | Mês de 1 a 12, ou 0 para o ano. Valor vazio apaga |
| Custo | `lancar_custo` | Categoria: aluguel, pessoal, marketing, sistemas, impostos, outros. Recorrente entra neste mês e nos seguintes. Não é comissão |
| Apagar um custo | `apagar_custo` | `confirmar=true`. Os outros meses da recorrência continuam |
| Parar a recorrência | `parar_recorrencia` | `confirmar=true` |
| Dia em que o mês vira | `salvar_fechamento` | 0 é o último dia do mês |
| Nome, cores, WhatsApp, modo da logo | `ler_identidade`, `salvar_identidade` | O arquivo da logo fica na tela. Modo: `preencher` ou `encaixar`. Cor em `#RRGGBB` |
| Vitrine | `listar_portfolio`, `publicar_roteiro` | Publicar ou retirar pede `confirmar=true` |

Cargo de consultor novo pede o gerente, se a agência usa gerente. Sem a pessoa dizer, pergunte. Não escolha um gerente sozinho.

Aceitar, cancelar, apagar, publicar, retirar e revogar só seguem depois de a pessoa confirmar nesta conversa.
