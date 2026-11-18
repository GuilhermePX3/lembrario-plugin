---
name: "lembrario-conector"
description: "Como trabalhar com os casos do lembrar.io pelo conector: escolher o caso, situar as notas no tempo, conferir fatos no registro e citar pelos IDs. Use quando o usuário perguntar algo sobre um caso guardado no lembrar.io (fatos, datas, quem disse o quê, conversas, e-mails, anexos, notas), pedir para buscar, conferir ou citar uma prova, pedir para montar ou mexer na Mesa, ou quando as tools nx_ do lembrar.io estiverem disponíveis na conversa."
---

# Trabalhar com o lembrar.io

O lembrar.io guarda cada caso do usuário com o que foi escrito (notas) e o registro do que aconteceu (conversas, e-mails e anexos). O conector dá acesso a esses casos pelas tools com prefixo `nx_`.

As instruções que o servidor manda no início de cada sessão valem sobre este texto. Se algo aqui parecer diferente delas, siga o servidor.

## 1. Escolher o caso certo

O conector serve todos os casos que o usuário liberou no link. Nas tools, o caso é o parâmetro `vault`: use o handle que aparece na lista.

1. Chame `nx_list_vaults` para ver os casos, a descrição de cada um e as fontes que ele tem (conversas, e-mails, anexos, mesa). Escolha o caso pelo pedido; se houver dúvida, pergunte ao usuário.
2. Antes de operar num caso pela primeira vez na conversa, chame `nx_get_vault_instructions` com o caso e siga o que vier: cada caso tem regras próprias.
3. Não misture casos: o que é de um não vai para outro sem o usuário pedir.

Um nome de tool citado sem o prefixo (nas instruções de um caso, numa nota) é a mesma tool com o prefixo: `read_note` é `nx_read_note`.

## 2. Situar no tempo

As instruções da sessão dizem que dia é hoje. As notas guardam datas absolutas (created, updated, date), que não envelhecem sozinhas: compare-as sempre com a data de hoje antes de tratar um conteúdo como atual.

`nx_list_notes` e `nx_search_notes` devolvem, por nota, `age` (idade legível), `age_days` (idade em dias) e `age_source` (de onde veio o sinal). Use esses campos antes de abrir a nota só para saber se ela ainda vale.

Nota antiga descreve o passado, não o estado presente. Ao usar conteúdo com `age_days` alto, diga ao usuário de quando ele é.

## 3. Orientar-se pelo mapa do caso

Chame `nx_get_vault_map` no início do trabalho num caso: é o inventário atual, gerado na hora a partir dos arquivos, com as notas mais referenciadas e as que mudaram por último.

Notas de índice (index.md, _Pasta.md, uma nota-mapa) são texto gravado e podem estar defasadas. Leia-as pelo contexto, mas confie no `nx_get_vault_map` para saber quais notas existem.

## 4. Fontes: as notas resumem, o registro prova

Um caso pode ter quatro fontes, conforme o que estiver ligado nele:
- **Notas**: o que foi escrito sobre o caso.
- **Conversas**: mensagens, áudios e mídias importados.
- **E-mails**: mensagens recebidas no endereço do caso, com o original e a assinatura conferida.
- **Anexos**: arquivos enviados, com a data do próprio documento e o texto extraído, transcrito ou lido por OCR.

As notas resumem; conversas, e-mails e anexos são o registro. Antes de afirmar um fato, confira no registro: abra o item com `nx_read_item` (ou a nota com `nx_read_note`) em vez de repetir o que uma nota diz sobre ele.

`nx_search` busca em todas as fontes de uma vez (palavra e significado), em todos os casos do link ou só nos que você indicar, e devolve cada item com o ID e o caso de onde veio.

## 5. Citar pelos IDs

Todo item tem um ID citável. Cite sempre assim:
- nota: [[caminho-da-nota]]
- conversa: [[conversa:<id>#0094]] (A007 áudio, M007 mídia)
- e-mail: [[email:E0007]], e um anexo do e-mail: [[email:E0007#anexo-2]]
- anexo: [[anexo:D0012]]

Use o ID que a tool devolveu; não monte um ID de memória.

## 6. A Mesa, quando estiver disponível

Quando a Mesa estiver disponível no caso (a fonte "mesa" aparece em `nx_list_vaults` e as instruções da sessão falam dela), ela é a sua área de trabalho para um objetivo, por exemplo "provar quem entrou na obra em março". Você cria áreas livres, coloca cartões e liga cartões (`nx_board_read`, `nx_board_edit`, `nx_board_remove`). O usuário vê a mesa se montar no painel e confirma ou rejeita.

Regras da Mesa:
- (1) cartão de evidência sempre aponta para um item real pelo ID; interpretação vai como cartão "leitura" e o que falta provar como "lacuna"
- (2) nunca ligue dois cartões sem dizer, na justificativa, o que em cada lado sustenta o vínculo
- (3) abra o original (nx_read_note, nx_read_item) antes de ligar
- (4) o que você cria fica "proposto" até o usuário decidir: não apresente como confirmado

Se o caso não tem Mesa, não tente usá-la: organize o trabalho na conversa ou numa nota, se o usuário pedir.

## 7. Skills do lembrar.io

As skills jurídicas do lembrar.io são `visual-law-juridico` (parecer com visual law) e `peticao-inicial` (petição inicial). Com este plugin elas já estão instaladas: quando o pedido casar com uma delas, siga a skill.

Se uma delas não estiver carregada na sua sessão, chame `nx_get_skill` com o nome e siga o texto que vier, como se a skill estivesse instalada. `nx_get_skill` sem nome lista o catálogo.

## 8. Limites

- Não invente fato, data, nome ou ID que não esteja no caso. O que faltar, diga que falta.
- Se o conector não responder ou o usuário não tiver acesso a um caso, diga isso ao usuário em vez de responder de memória.
