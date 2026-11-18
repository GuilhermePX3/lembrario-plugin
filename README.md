# lembrar.io para o Claude

Este repositório distribui o plugin do [lembrar.io](https://lembrar.io) para o Claude. Ele contém somente o plugin (manifesto, configuração do conector e skills); o código do lembrar.io não fica aqui.

O plugin conecta o Claude aos seus casos no lembrar.io, com notas, conversas, e-mails e anexos, e traz skills que ensinam o Claude a trabalhar com eles: a skill de uso do conector, parecer com visual law e petição inicial cível.

## Instalar

**No claude.ai e no Claude Desktop:** em Personalizar > Plugins > Adicionar > Adicionar marketplace, informe a URL deste repositório. Depois instale o plugin **lembrario** e conecte o conector na aba Conectores, entrando com a sua conta do lembrar.io.

**No Claude Code:**

```
claude plugin marketplace add GuilhermePX3/lembrario-plugin
claude plugin install lembrario@lembrario
```

**Só o conector, sem o plugin:** adicione um conector personalizado com a URL `https://conn.lembrar.io/mcp`.

## Dados

O conector envia ao servidor `conn.lembrar.io` as consultas e as notas que o Claude lê ou grava nos seus casos, sempre com a sua conta, autenticada por login (OAuth). As skills são instruções em texto e não enviam dados a lugar nenhum.

## Suporte

suporte@lembrar.io

## Licença

Todos os direitos reservados. Veja `plugins/lembrario/LICENSE`.
