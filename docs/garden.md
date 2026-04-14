# O que é um Jardim Digital (Digital Garden)?

Um Jardim Digital é uma abordagem para criar e manter conteúdo na internet que funciona de forma muito diferente do modelo tradicional de blog. 

Enquanto um blog é focado em publicações cronológicas ("stream"), onde os textos nascem 100% finalizados e vão sendo empurrados para as páginas antigas com o tempo, o Jardim Digital se comporta como um espaço de cultivo orgânico. Nele, as informações são interligadas e crescem de forma não-linear ao longo do tempo.

## Como Funciona

Em um Jardim Digital, os artigos e notas são organizados por seu "estágio" de maturidade, utilizando metáforas botânicas. Você pode publicar um texto mesmo que ele tenha apenas duas frases de anotação solta, sem medo e sem sentir a pressão de entregar um texto perfeito de primeira. À medida que você estuda ou reflete sobre o assunto ao longo dos meses ou anos, você revisita a página e a reescreve, ajudando a ideia a "crescer".

### Os Estágios de Cultivo

O plugin local traduz nativamente as tags específicas de jardinagem. Veja o que cada uma significa:

* 🌱 **Seedling (Semente/Muda)** - Utilizando a tag `garden/plant`
  Uma ideia no estágio mais inicial possível. Um rascunho rápido, um pensamento solto ou uma anotação básica e bruta. As pessoas que acessam o site percebem que você ainda vai elaborar isso no futuro.
  
* 🌿 **Growing (Cultivo/Crescendo)** - Utilizando a tag `garden/cultivate`
  Anotações que já possuem algum corpo e que você tem pesquisado, escrito e estruturado ativamente no presente.

* 🌳 **Evergreen (Perene/Forte)** - Utilizando a tag `garden/evergreen`
  O texto atingiu a sua maturidade, tem fontes de citação e parágrafos completos. Não exigirá grandes melhorias (apenas pequenos ajustes no futuro).

* ❓ **Open Question (Pergunta em Aberto)** - Utilizando a tag `garden/question`
  Para criar posts a partir de uma dúvida que você tem e não sabe a resposta no momento.

* 🪴 **Repotting (Replantando)** - Utilizando a tag `garden/repot`
  Sinaliza que o artigo precisa ser reestruturado profundamente. Era complexo demais ou mudou de premissa.

* ✨ **Revitalizing (Revitalizando)** - Utilizando a tag `garden/revitalize`
  Um texto ou rascunho mais antigo que foi recuperado e está sendo repaginado.

* 🔄 **Revisit (Revisitar)** - Utilizando a tag `garden/revisit`
  Uma bandeira de aviso para você próprio (e para os leitores): este conteúdo precisa ser validado de novo em algum dia.

## Como Participar e Praticar

Praticar o "Digital Gardening" utilizando o Obsidian juntamente com o seu site pessoal é extremamente prático porque o seu site acompanha o crescimento "biológico" da sua anotação no aplicativo.

### O Ciclo Prático

1. **Plante a ideia**: Comece a escrever uma nova nota no Obsidian. Pode ser sobre qualquer assunto de interesse rápido.
2. No seu Frontmatter (o bloco de configurações no topo da página `---`), insira o estágio de muda:
   ```yaml
   tags:
     - garden/plant
   ```
3. Publique sua nota no site pelo Obsidian. O plugin comunicará que o estágio deste post é Plantado.
4. **Cultive**: Semanas ou dias depois, caso queira voltar para reescrevê-lo, você não publica um post repetido: Você abre a mesma nota. Substitui a tag para `garden/cultivate`. Adiciona os parágrafos adicionais e links e publica na mesma página.
5. **Cresça**: Quando seu artigo estiver excepcional, profundo e claro, mude a tag para `garden/evergreen`. Na mesma hora o site vai exibir o novo estágio maturo final. 

**Vantagem da Integração:** O plugin identifica nativamente se o seu artigo se tornou _evergreen_. Da primeira vez que ele é enviado nesta fase botânica final, ele insere ocultamente para o site o momento exato em que virou adulto e perene!

O Jardim se desenvolve repensando e alterando textos — cultive o hábito de revisar páginas velhas!
