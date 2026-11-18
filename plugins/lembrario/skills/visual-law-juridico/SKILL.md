---
name: "visual-law-juridico"
description: "Cria documento jurídico com visual law (parecer, petição, anexo de fatos, relatório ao cliente): entrevista o advogado, propõe a estrutura matriz e monta com prova conferida no original."
---

# Visual law jurídico

Visual law é uma camada de apresentação aplicada a um gênero jurídico: parecer, petição, anexo de fatos, contrato ou relatório ao cliente. "Parecer com visual law" é pedido comum e válido. O gênero define o conteúdo. O visual law define como o leitor encontra e confere esse conteúdo.

Nunca comece pelo layout. A ordem é sempre: entrevista, estrutura matriz aprovada, coleta e conferência da prova no original, montagem no canvas, PDF nos marcos, verificação.

## 1. Entrevista (antes de qualquer leitura ou escrita)

Use a ferramenta de perguntas de múltipla escolha quando existir; senão, pergunte em texto. No máximo 4 perguntas por vez. Pule as que o pedido já respondeu. Ofereça sempre uma opção recomendada.

Bloco A, obrigatório:
1. **Gênero**: parecer com visual law; petição com visual law; anexo visual de fatos (juntado à peça); relatório ao cliente; outro.
2. **Leitor**: juiz ou tribunal; parte contrária ou mediação; cliente leigo; uso interno do escritório.
3. **Objetivo**: provar fatos; sustentar uma tese; explicar riscos e estratégia; propor acordo.
4. **Pedido ou conclusão**: já definido (qual); deixar como campo da advogada; não se aplica.

Bloco B, quando relevante:
5. **Identidade visual**: design system do escritório, se existir; papel timbrado (pedir arquivo ou extrair de documento anterior); layout neutro.
6. **Extensão**: 1 página; até 8 páginas; sem limite.
7. **Formato final**: PDF A4; Word editável; ambos.
8. **Recorte**: caso inteiro; um tema só (qual).

Regras que derivam das respostas:
- Leitor juiz ou parte contrária: só fatos com prova. Sem leitura do assistente, sem pontos fracos, sem estratégia.
- Uso interno: inclui riscos, pontos fracos, lacunas e leituras identificadas por autor.
- Cliente: linguagem leiga; termo técnico explicado na primeira vez.

## 2. Estrutura matriz (mostrar e aprovar antes de montar)

Mostre o sumário página a página, uma linha por seção. Ajuste e só então siga.

### Parecer com visual law
1. Capa: consulentes, parte contrária, objeto, data, natureza
2. Em síntese: 3 a 5 conclusões e até 3 números-chave
3. Fatos: linha do tempo com prova por linha
4. Fundamentação: tema, norma, o que diz, como incide no caso
5. Argumentos da parte contrária e resposta
6. Riscos e pontos fracos, com alcance e mitigação
7. Lacunas de prova
8. Proposta de atuação
9. Prazos
10. Conclusão e assinatura

### Anexo visual de fatos (para o juiz)
1. Ficha do caso, o caso em 5 fatos, campo do pedido, legenda das fontes
2. O fato central em linha do tempo hora a hora, com a prova visual ao lado
3 a 6. Um tema por página: cronologia, citação literal, imagem, fonte
7. Prova técnica (laudo) por sistema
8. Quadro de provas: afirmação, fonte, tipo, códigos de verificação

### Petição com visual law
Síntese visual na primeira página; fatos em linha do tempo; quadros norma x caso; pedidos numerados e destacados; quadro de documentos. O texto argumentativo é da advogada.

### Relatório ao cliente
O que aconteceu; onde estamos; próximos passos com datas; o que o cliente precisa fazer; riscos em linguagem simples.

## 3. Coleta e conferência da prova

**Regra central: nota que cita item de conversa é ponteiro, não prova.** Nenhuma citação de conversa entra na peça vinda só de uma nota, mesmo marcada como "conferida". "Conferido" só vale quando a janela em volta do item foi lida.

**Hierarquia das fontes:**
- Sobre o que foi dito, por quem e quando, vale a conversa. Se a nota diverge dela nisso, diga a divergência e use a conversa.
- Fato de outra fonte (laudo, ata notarial, e-mail, visita presencial, contrato) vale pela fonte própria, mesmo que a conversa não fale dele. Confira nessa fonte.
- Fato posterior ao último export da conversa não está nela. Não conclua que não aconteceu.
- Arquivo original de áudio prevalece sobre correção humana registrada, que prevalece sobre a transcrição automática.
- A conversa prova que alguém disse algo, não que o dito é verdade.

Com o lembrar.io conectado (get_vault_map, list_conversations, read_conversation, search_conversation, read_item):
1. Orientação: get_vault_instructions e get_vault_map. Índices gravados podem estar velhos; confie no mapa.
2. list_conversations: veja o período de cada exportação e o aviso de export defasado.
3. list_anchors: comece pelos itens marcados pelos advogados.
4. Notas de tese: leia para saber **onde** procurar, não para copiar citação. Se a nota vier com aviso de ser anterior à importação, confira cada trecho copiado.
5. Para cada citação de conversa que vai à peça:
   a. read_item no ID: texto inteiro, transcrição com minutagem, imagem e aviso de arquivo encaminhado.
   b. read_conversation com from/to cobrindo de 3 a 10 mensagens antes e depois. É aí que aparecem o sentido real e as provas vizinhas.
   c. Se o aviso disser que o arquivo pode ser encaminhado, confirme com o usuário quem fala antes de atribuir a fala.
6. search_conversation: termo exato para nomes e frases; sem termo exato para temas; com person para mapear onde alguém aparece.
7. Imagem sem leitura na importação: leia você mesmo e marque, no documento e em qualquer nota, que a leitura é do assistente.
8. Fato que a nota atribui a uma conversa e que não aparece nela sai da peça e vai para a lista de não confirmados. Fato de outra fonte não sai por isso; confira na fonte própria.
9. Ao atualizar uma nota, não copie a fala. Cite o item com [[conversa:<id>#0123]], ou o intervalo [[conversa:<id>#0120..#0130]] quando o sentido depende das vizinhas.

Anotações na conversa:
- Pode marcar ★ e gravar observação própria em item decisivo, separando o que está provado do que é hipótese.
- Nunca editar observação do usuário. Se ele pedir revisão, entregar o texto para ele colar.

Sem o lembrar.io: trabalhe só com os documentos anexados e peça o que faltar. Não preencha fatos por suposição.

**Toda a coleta acontece antes da montagem.** É a etapa mais cara do trabalho; não repita leituras de conversa a cada edição de layout.

## 4. Regras de prova

- Toda afirmação de fato traz a fonte: conversa, número da mensagem, data e hora. Áudio com o trecho em minutos. Documento com a página.
- No chat e em documento interno, cite o item com o link que a ferramenta devolver. Em peça para terceiros, o link não substitui ID, data, hora e código de verificação.
- Selo de prova ao lado de cada fonte:
  - **Fé pública ou ART**: ata notarial, laudo assinado, matrícula, certidão
  - **Original**: mensagem, áudio, foto ou vídeo no arquivo original
  - **A juntar**: prova indicada, ainda não anexada
  - **Hipótese**: só em documento de uso interno; nunca como fato
- Transcrição de áudio e leitura de imagem por máquina ou pelo assistente: avisar que o original prevalece.
- Citação literal entre aspas, corte marcado por [...]. Nunca juntar trechos de mensagens diferentes numa só citação.
- Proximidade no tempo não é mesmo assunto. Não encadear duas mídias sem confirmar pelo conteúdo.
- Nunca inventar norma, súmula, processo ou julgado. Na dúvida, [VERIFICAR].
- Paráfrase de laudo fica marcada como paráfrase até a advogada trocar pela frase literal com página.
- Respeitar as decisões de omissão registradas no caso (o que não entra na peça).
- Incluir códigos de verificação (SHA-256) das exportações e dos arquivos citados, quando disponíveis.

## 5. Componentes visuais

Use só os que o conteúdo pede:
- **Linha do tempo**; hora a hora quando o intervalo curto for o argumento
- **Citação com fonte**: fala literal em destaque, fonte embaixo
- **Prova visual ao lado do texto**: print ou quadro de vídeo, legenda com ID, data e arquivo original
- **Números-chave**: no máximo 3 por página, cada um com o que mede
- **Quadro alegação x prova**: só com alegações que a outra parte fez por escrito
- **Fluxo**: etapas de um processo
- **Quadro de provas** na última página

Evitar: ícones decorativos, gráfico sem dado, cor como único portador de sentido, página com uma linha só.

## 6. Montagem: canvas como fonte, PDF nos marcos

### 6.1 Identidade visual
- Se o escritório tem design system (artifact do tipo Design System com logo, cores, fontes, papel timbrado e margens da área útil), parta dele. Liste os design systems disponíveis antes de perguntar.
- Se não tem, extraia logo e cores de um documento anterior do escritório e ofereça, em uma linha, criar o design system para os próximos documentos.
- Papel timbrado como fundo de página; conteúdo dentro da área útil entre cabeçalho e rodapé.

### 6.2 Canvas é a fonte de trabalho
- Monte no canvas (artifact do tipo Design, páginas A4 fixas), quando o tipo estiver disponível na conta.
- Monte uma página por vez e publique cada página pronta, para o advogado acompanhar e corrigir cedo.
- Edite por trecho: mude só o que foi pedido. Nunca regenere o documento inteiro para um ajuste.
- Lembre o advogado, uma vez, de que ele pode corrigir texto direto no canvas, sem pedir ao assistente.
- Uma ideia por página. Título que afirma o fato, não o tema. Frases curtas, voz ativa, palavras comuns. Sem travessão longo.

### 6.3 PDF só nos marcos
Gere ou exporte PDF apenas em três momentos:
1. versão para revisão do advogado;
2. versão revisada;
3. versão final, a que vai aos autos ou ao cliente.

- Nome do arquivo com versão e data: `<caso>-<genero>-v1-AAAA-MM-DD.pdf`. Os PDFs dos marcos ficam como registro do que foi enviado e quando.
- O próprio advogado pode baixar o PDF pelo canvas. Na maior parte das versões, o assistente não precisa renderizar.
- **Antes do primeiro marco que vai a terceiros, teste o PDF exportado:** o texto precisa ser pesquisável (selecionável), não imagem. Se não for, gere esse marco pelo caminho HTML (6.4).
- Peça destinada a tribunal: confira o limite de tamanho por arquivo do sistema do tribunal e comprima as imagens antes do PDF final.

### 6.4 Caminho alternativo: HTML para PDF
Use quando o canvas não estiver disponível ou quando o PDF exportado não for pesquisável:
- HTML com CSS de impressão (`@page { size: A4; margin: 0 }`), papel timbrado como fundo da página, imagens locais.
- Renderize em PDF A4 com navegador headless.
- Mantenha o HTML como fonte e edite por trecho, como no canvas.

## 7. Verificação

A cada edição:
- Olhe só as páginas que mudaram. Conferir o documento inteiro a cada ajuste é o maior desperdício de contexto.

Antes de cada marco:
1. Renderize e olhe todas as páginas: nada invadindo cabeçalho ou rodapé, nenhuma página quase vazia.
2. Para cada citação de conversa: o item foi aberto e a janela em volta foi lida? Se não, abrir agora.
3. Para cada fato de outra fonte: foi conferido na própria fonte?
4. Documento para juiz sem leitura, tese ou ponto fraco.
5. PDF com texto pesquisável e tamanho dentro do limite do destino.
6. Entregar com uma lista curta: o que está a juntar, o que não foi confirmado e o que o advogado precisa revisar (transcrições, paráfrases de laudo, pedido).