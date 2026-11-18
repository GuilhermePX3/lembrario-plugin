# lembrar.io para o Claude

O lembrar.io guarda o que foi dito num caso, com prova: notas, conversas importadas, e-mails recebidos no endereço do caso e anexos. Este plugin liga o Claude aos seus casos e traz as skills que ensinam o Claude a trabalhar com eles.

## O que o plugin traz

- **Conector do lembrar.io**: dá ao Claude acesso aos casos da sua conta, para ler, buscar e, quando você permitir, escrever notas e montar a Mesa.
- **Skill `lembrario-conector`**: como escolher o caso certo, conferir cada fato no registro antes de afirmar e citar pelos IDs do lembrar.io.
- **Skill `visual-law-juridico`**: parecer, petição, anexo de fatos ou relatório ao cliente com visual law, com a prova conferida no original.
- **Skill `peticao-inicial`**: minuta de petição inicial cível pelo procedimento comum do CPC.

## Instalar

No claude.ai e no Claude Desktop: Personalizar > Plugins > Adicionar > Adicionar marketplace, com `GuilhermePX3/lembrario-plugin`; depois instale o plugin lembrar.io e conecte o conector na aba Conectores.

No Claude Code:

```
/plugin install lembrario --marketplace GuilhermePX3/lembrario-plugin
```

## Como usar

1. Instale o plugin e, na aba de conectores do plugin, conecte o lembrar.io.
2. Entre com a sua conta do lembrar.io quando o Claude pedir. Não há chave nem senha para configurar no plugin.
3. Peça ao Claude o que precisa sobre um caso, por exemplo: "monte a linha do tempo do caso com as provas" ou "faça um parecer com visual law".

O Claude escolhe sozinho a skill que casa com o pedido. Você vê no lembrar.io tudo o que ele escreve, e o que ele propõe na Mesa só vale depois que você confirma.

## Que dados o plugin envia e para onde

O plugin não roda programa nenhum no seu computador: são só textos (skills) e o endereço do conector.

O conector fala com um único servidor, `https://conn.lembrar.io/mcp`, operado pelo lembrar.io. Por ele vão os pedidos que o Claude faz em seu nome, como buscas, leituras e as notas que ele grava, e voltam os conteúdos dos seus casos: notas, conversas, e-mails e anexos. Esse conteúdo entra na conversa com o Claude para que ele responda. O acesso é o da sua conta, com o login que você faz no lembrar.io, e você pode desconectar quando quiser.

As skills não enviam nada: são instruções que o Claude lê.
