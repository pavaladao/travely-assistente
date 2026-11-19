# Assistente Travely

A pessoa fala com o harness e manda instalar por este repositório:

> Instale o assistente Travely por https://github.com/pavaladao/travely-assistente

O assistente baixa esta pasta, copia as skills, grava o texto permanente e liga o Travely. A pessoa só informa a URL e o token.

## Para o assistente que está instalando

Faça a instalação na pasta que está aberta. Não peça para a pessoa copiar arquivo.

Se essa pasta já tiver um `AGENTS.md` que não começa com `# Assistente do Travely`, pare e pergunte se a instalação é nesta pasta. Não substitua a instrução de outro projeto.

### 1. Skills

Se `skills/configurar-agencia/SKILL.md` já estiver nesta pasta, use esta cópia. Senão, baixe o repositório:

```bash
git clone --depth 1 https://github.com/pavaladao/travely-assistente.git
```

Copie cada pasta de `skills/` para o destino do harness. Crie o destino se não existir. Na atualização, substitua essas pastas.

| Harness | Destino das skills |
| --- | --- |
| Cursor, Codex, Copilot | `.agents/skills/` |
| Claude Code | `.claude/skills/` |

Se não der para saber qual é o harness, copie para os dois destinos.

Quando o comando existir, ele faz a mesma cópia:

```bash
gh skill install pavaladao/travely-assistente --all --agent cursor
gh skill install pavaladao/travely-assistente --all --agent claude-code
gh skill install pavaladao/travely-assistente --all --agent codex
```

Use o `--agent` do harness desta conversa. Cursor, Codex e Copilot compartilham `.agents/skills/`.

As nove pastas são `configurar-agencia`, `comecar-o-dia`, `criar-viagem`, `lancar-venda`, `cuidar-proposta`, `criar-roteiro`, `baixar-fotos`, `ler-financeiro` e `administrar-agencia`.

### 2. Texto permanente

Copie o `AGENTS.md` deste repositório para a raiz da pasta aberta.

No Claude Code, grave o mesmo texto em `CLAUDE.md`. Se `CLAUDE.md` já existir, acrescente no final: `Siga o AGENTS.md desta pasta.`

### 3. Ligação

Pergunte, numa mensagem só, a URL do Travely e o token. Sem os dois, a instalação para aqui.

A URL do servidor é a do site com `/mcp` no final. Se a pessoa já mandou esse caminho, use como está. O header é `Authorization` com o valor `Bearer` e o token. Não invente URL nem token. Não repita o token na resposta. Não grave o token no git: se a pasta for um repositório, deixe o arquivo da ligação no `.gitignore` antes de qualquer commit.

Cursor, em `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "travely": {
      "url": "https://HOST/mcp",
      "headers": {
        "Authorization": "Bearer TOKEN"
      }
    }
  }
}
```

Claude Code, no diretório da pasta aberta. O escopo `local` guarda o token fora do git:

```bash
claude mcp add --transport http --scope local travely https://HOST/mcp --header "Authorization: Bearer TOKEN"
```

Codex, em `.codex/config.toml` da pasta aberta. Se o arquivo já tiver outros servidores, só acrescente esta tabela:

```toml
[mcp_servers.travely]
url = "https://HOST/mcp"
http_headers = { Authorization = "Bearer TOKEN" }
```

Outro harness: o formulário de MCP desse produto, com a mesma URL e o mesmo header.

### 4. O que fica de fora

Não crie `perfil.md`. A primeira conversa grava o nome, o público e o tom. Não copie `.cursor/` deste repositório.

### 5. Feche

Diga que as nove skills, o texto permanente e a ligação estão no lugar. Peça um chat novo. Sem perfil, esse chat só configura a agência.
