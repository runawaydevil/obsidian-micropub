# Manual de Uso: Micropub Publisher (para Obsidian)

O **Micropub Publisher** é um plugin do Obsidian criado para publicar suas notas diretamente para qualquer servidor compatível com **Micropub** (Indiekit, Micro.blog, WordPress com plugin Micropub instalado, etc.).

---

## 📥 1. Instalação

### Visão Geral
Você pode adicionar este plugin manualmente no diretório de plugins do seu cofre (Vault) do Obsidian.

### Passos:
1. Faça o download da versão mais recente disponível (arquivos `main.js` e `manifest.json`).
2. Acesse a pasta do seu cofre no computador e navegue até `.obsidian/plugins/`.
3. Crie uma pasta chamada `obsidian-micropub` e cole os dois arquivos nela.
4. Reinicie o seu Obsidian. Vá em **Configurações > Plugins da Comunidade**, encontre o "Micropub Publisher" e clique em **Ativar**.

---

## ⚙️ 2. Configurando o Plugin

Uma vez habilitado, vá até a aba de opções do Micropub Publisher no seu Obsidian.

### Login via IndieAuth (Recomendado)
A forma mais segura e fácil de conectar seu site:
1. Digite a URL do seu site (Ex: `https://meu-site.com`) no campo **Site URL**.
2. Clique em **Sign in** (Entrar). Isso vai abrir o seu navegador tradicional na página de login do seu provedor IndieAuth.
3. Autorize o login. O navegador redirecionará automaticamente de volta para o Obsidian e seu Token de Acesso será salvo com as permissões corretas.

### Token Manual (Avançado)
Se por acaso o IndieAuth não funcionar, expanda a opção **Or paste a token manually** (Ou cole um token manualmente) e insira o seu `Bearer Token` lá diretamente. Certifique-se que o token tenha as permissões (escopos) de `create update media`.

---

## ✍️ 3. Como Escrever e Publicar

O segredo do plugin é que ele mapeia as **Propriedades (Frontmatter)** inseridas no topo de cada nota.

### Notas (Notes) vs Artigos (Articles)
O plugin descobre e diferencia automaticamente o formato do seu texto com base no seu preenchimento:

* **Artigo (Article):** Adicione a propriedade `title` ou `name` nas propriedades. Isso indica que será uma publicação centralizada, em textos longos, possuindo um título principal real no site.
* **Nota (Note):** Apenas inicie seu texto sem as propriedades de título. Neste caso, atua como um 'microblog', muito semelhante do um formato de uma mensagem no Twitter ou Mastodon.

> [!TIP]
> **Forçando o Formato Manualmente:** Use e preencha especificamente na sua nota a propriedade `postType` com o valor de `article` ou de `note` caso queira anular o comportamento inteligente automático acima.

### Categorias e Tags
Usar etiquetas normais nas Propriedades ou pelo formato (`#tag` no corpo da nota) já as converterá automaticamente como se fossem `categories` no Micropub durante todos os seus envios.

---

## 🖼️ 4. Imagens e Fotos

Você pode colocar fotos nas suas anotações com o uso do anexo e links normais:
* Se você adicionar na nota algo usando um caminho para o seu computador ou cofre: `![[imagem.png]]`, na hora que clicar no comando de publicar o texto para a internet, o próprio sistema fará um upload da mídia e converterá aquele código interno do Obsidian por uma imagem com link online real: `![imagem](https://seu-site.com/media/imagem.png)`.

---

## 🌱 5. Fluxo de Trabalho para "Jardim Digital" (Digital Garden)

Você pode mapear em qual ciclo os seus artigos estão! O plugin já captura "Tags de Fase".

Ao colocar as tags do Obsidian abaixo, ele as envia para plataforma como a propriedade Micropub respectiva:

| Tag adicionada no Obsidian | Como reflete no "Digital Garden" |
| :--- | :--- |
| `#garden/plant` | 🌱 Muda/Rascunho Inicial (`plant`) |
| `#garden/cultivate` | 🌿 Desenvolvendo e Cultivando (`cultivate`) |
| `#garden/evergreen` | 🌳 Artigo Completo/Sempre-verde (`evergreen`) |
| `#garden/question` | ❓ Questão Aberta (`question`) | 
| `#garden/repot` | 🪴 Reestruturando Arquitetura (`repot`) |
| `#garden/revitalize` | ✨ Revitalizando a página (`revitalize`) |
| `#garden/revisit` | 🔄 Pendente de Visitação/Edição (`revisit`) |

---

## 🔄 6. Interações Sociais (Likes, Reposts e Replys)

Envie interações da IndieWeb colocando as seguintes propriedades:

* `like-of`: Link da página caso seu post seja um "*Favoritar/Curtir*" para outra pessoa.
* `repost-of`: O link caso seu objetivo é disparar o evento de "*Repostar*".
* `in-reply-to`: Para disparar um comentário/resposta em uma notícia de outro website. Se adcionar um corpo em texto normal com isso ativado o post sai preenchido como uma citação base da página original!

---

## 🤖 7. Sinalizando Transparência em Inteligência Artificial

Deixe seus próprios leitores seguros, avisando em suas propriedades de como usou ferramentas baseadas na nuvem:

* `ai-text-level`: Define qual foi o nível de envolvimento: "0" (Desligado e Autoral), "1" (Revisão da IA e editorial), "2" (Conteúdo foi meio a meio co-criado) ou "3" (Geração completamente Artificial).
* `ai-tools`: Um campo pequeno preenchível indicando os softwares utilizados (Ex: `"Claude"`, `"Copilot"`).

---

## 🚀 8. E Depois que Mando Publicar?

Uma funcionalidade matadora é o seu Writeback.
Se a opção **Write URL back to note** (Gravar URL na nota de volta) lá naquelas opções do seu Plugin na Configuração principal estiver ligada (já está por padrão), acontecerá isto: 

Imediatamente após a entrega da nota em seu site a internet o Obsidian injetará **uma linha nova em seu front-matter chamada `mp-url`**, como abaixo:

`mp-url: "https://meu-site/blog/minha-primeira-pagina-top"`

> [!WARNING]
> **Editando textos já online:** Nunca delete de bobeira a propriedade `mp-url` que apareceu! Toda nova tentativa de publicar o mesmo post será feita verificando este link. Com ele ali, em vez de enviar um artigo publicando *"De Novo"*, ele enviará apenas um comando silencioso de **Update** alterando o texto/anexos na internet.
