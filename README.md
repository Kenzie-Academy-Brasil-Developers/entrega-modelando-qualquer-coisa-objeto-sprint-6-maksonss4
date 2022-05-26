Esta aula não possui exemplos de código porque serve para ajudá-lo a desenvolver sua intuição sobre objetos e a criação deles, em vez de ensinar padrões de sintaxe ou de código. Se você conseguir desenvolver uma intuição forte sobre o propósito dos objetos, a estrutura e o uso deles objetos não parecerá tão misterioso.

Os objetos são o alicerce do JavaScript. Até mesmo funções herdam do soberano objeto Object do JavaScript (que é o motivo pelo qual você consegue passar funções em forma de objeto de maneira tão útil e porque as funções possuem métodos de protótipo, como `bind`, `call` e `apply`). Os objetos são incrivelmente flexíveis. Mas às vezes, com flexibilidade extra vem um pouco de complexidade extra.

É tipo yoga: quanto mais a flexibilidade dos praticantes aumenta, mais aumenta a profundidade deles, até que finalmente um dia você está falando com um instrutor de yoga e de repente você se vê em um plano superior através da profundidade absoluta da conversa. (*Advertência: a yoga não necessariamente torna uma pessoa profunda ou "profunda"*.)

Dominar o uso dos objetos levará um tempo, mas você já está no caminho certo e vale muito a pena.

Precisamos de objetos no JavaScript porque eles nos permitem fazer algo chamado "modelagem". A ideia por trás da modelagem é que possamos representar coisas e ideias como uma lista de nomes de propriedade sem que nenhuma regra de ordenamento ou de organização seja imposta.

Para ilustrar esta ideia, vamos ler a descrição que um desenvolvedor fez de si mesmo. O desenvolvedor irá contar alguns detalhes da vida dele. As pessoas são coisas complicadas, com pensamentos e ações, e vidas cheias de profundidade (assim como um instrutor de yoga ou um Objeto JavaScript). Ao ler o seguinte parágrafo, procure detalhes sobre o autor com os quais poderíamos modelar como um conjunto de propriedades.

> "Olá, meu nome é Bennie Marenghi. Eu moro no norte de Rhode Island com minha esposa Bernice, nossa filha Moneta e nosso filho Garth. Nos últimos cinco anos, tenho trabalhado como autônomo. Gosto de trabalhar em grupos de desenvolvimento por um tempo e depois partir para outros projetos. Me deparar com coisas novas de tempos em tempos é empolgante. Eu acho que já trabalhei em 8 equipes nos últimos cinco anos. Em coisas bem legais. Quando não estou programando, gosto muito de acampar com a família."

Bennie nos deu várias informações sobre a vida dele que podemos usar para construir um modelo dele como um objeto. Vamos dividir este parágrafo e procurar por detalhes que podemos representar com propriedades. Normalmente, me concentro em informações que posso traduzir diretamente como uma `chave` ou `valor`.

Para demonstrar isso, vou realçar as palavras do parágrafo *que se destacam como valores de propriedades*.

> "Olá, meu nome é **Bennie Marenghi**. Eu moro no norte de **Rhode Island** com minha esposa **Bernice**, nossa filha **Moneta** e nosso filho **Garth**. Nos últimos **cinco anos**, tenho trabalhado como **autônomo**. Gosto de trabalhar em grupos de desenvolvimento por um tempo e depois partir para outros projetos. Me deparar com coisas novas de tempos em tempos é empolgante. Eu acho que já trabalhei com **8** equipes nos últimos **cinco anos**. Em coisas bem legais. Quando não estou programando, gosto muito de **acampar com a família**."

Agora, vamos extrair todos estes detalhes do parágrafo e reescrevê-los em forma de uma lista simples: Na prática, estamos removendo todo o "preenchimento" da explicação de Bennie e listando apenas os detalhes exatos do que ele nos forneceu. Lembre-se, esses detalhes são os *valores* das nossas propriedades.

* Bennie Marenghi
* Rhode Island
* Bernice
* Moneta
* Garth
* cinco anos
* autônomo
* 8
* acampar com a família

Agora vamos alterar nossa lista de valores e torná-los propriedades. Para fazer isso, teremos que associar cada valor a uma chave.

* nome: Bennie Marenghi
* residência: Rhode Island
* esposa: Bernice
* filha: Moneta
* filho: Garth
* experiência: cinco anos
* ocupação: autônomo
* equipes: 8
* hobby: acampar com a família

Para algumas de nossas propriedades, Bennie nos deu nomes de chaves bem razoáveis. Por exemplo, a primeira frase é: "Olá, meu nome é Bennie Marenghi." Nessa frase, ele forneceu "nome" e "Bennie Marenghi". "nome" já é a chave perfeita para o valor "Bennie Marenghi".

Para outros detalhes, Bennie nos deu o valor, mas não deu a chave. Nesses casos, temos que escolher uma chave que faça sentido com o valor. Por exemplo, na última frase, ele nos diz que quando não está trabalhando, está acampando com a família - o que significa que, de certa forma, ele continua trabalhando: mas dessa forma ele pode fazer usando repelente de mosquitos e um chapéu de fazendeiro que dá para reconhecer de longe. Isso é ótimo, mas temos que dar um tipo de identificação para isso. Eu escolhi "hobby", mas poderia ter escolhido "passatempo" ou "férias". Todas as três opções fazem sentido, mas achei "hobby" mais apropriado.

## Mais Exemplos

Qualquer coisa pode ser modelada como uma propriedade, então você deve praticar isso. Nesta seção, você lerá alguns parágrafos. Sua tarefa é modelar o sujeito do parágrafo como uma lista de propriedades.

Ao passar o mouse sobre as seguintes descrições, você encontrará modelos completos para cada uma delas. Se sua modelagem for um pouco diferente dos exemplos fornecidos, não se preocupe. Você pode usar uma palavra diferente para sua chave, ou escolher detalhes diferentes para incluir em sua lista de propriedades. O objetivo deste pequeno exercício é fornecer alguma experiência em *pensar sobre modelagem*.

> **OBSERVAÇÃO: Tente completar sua modelagem antes de olhar os exemplos passando o mouse sobre o texto. É importante que você tente.**

### Descrição 1 - Modelar o Jarro

<blockquote title="cor: azul, cabo: longo, bico: pequeno, altura: 35, volume: 900ml, material: vidro translúcido espesso, peso: pesado, usabilidade: um tanto quanto pesado e difícil de manusear"> "O jarro é azul e possui um cabo longo e um pequeno bico usado para servir. Ele tem 35 cm de altura e pode conter cerca de 900 ml. O vidro é translúcido para que você possa ver o conteúdo. O vidro é espesso, tornando o jarro um tanto quanto pesado e difícil de manusear."
</blockquote>

### Descrição 2 - Modelar o Cachorro

<blockquote title="Sadie, genero: feminino, pelo: preto, raça: labrador, disposição: super amigável e dócil com as crianças, treinamento: Doggy Daze, treinador: Donald Johnson, peso: 30kg"> "Sadie é o melhor cão do mundo! Seu pelo tem a capa preta mais linda que eu já vi em um labrador. Ela é super amigável e dócil com as crianças. Eu a levei para ser treinada profissionalmente na Doggy Daze em Columbia, que fica na esquina da minha casa. Seu treinador foi Donald Johnson, e ele é um dos melhores. Sadie é uma cadela grande, pesa quase 30 kg, então dava um pouco de trabalho antes de Donald a treinar. Agora ela é o melhor cão do mundo!"
</blockquote>
