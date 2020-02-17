---
layout: post-ads
title:  "Eu realmente preciso aprender a linguagem antes do framework?"
categories: [ programacao, iniciantes ]
image: assets/images/planta.png
author: leo
tags: [ programacao, dicas, iniciantes, linguagens, frameworks ]
---
Geralmente, quando alguém me pergunta: *"Léo, devo começar aprendendo o framework A ou B?"*, minha resposta é: *"Quanto você sabe da linguagem base do framework?"*. E, quase sempre, a resposta é "pouco" ou "quase nada". Entender isso é a diferença entre começar a construir uma casa pelo telhado ou pela fundação.

Na maior parte da vezes, nós queremos construir programas e sites em uma velocidade extremamente rápida, para gerar valor para o cliente e nos trazer o retorno financeiro que queremos. E isso é extremamente válido, não me interprete mal. O ponto que trago é: como você saberá se está fazendo algo certo, se não sabe como é "o certo"?

Para este artigo, vou utilizar como exemplo o [PHP][php], linguagem que eu domino e tenho mais intimidade. No entanto, os conceitos que vou mostrar se aplicam a todas as outras linguaguens.

Comecemos por onde todos em programação deveriam começar: lógica de programação. Não importa se você vai aprender por meio de [fluxogramas][fluxograma], [Portugol][portugol] ou [VisualG][visualg], você PRECISA saber lógica, obrigatoriamente. Sem ela, nenhum dos seus programas irão funcionar da forma adequada e você, muito provavelmente, estará fadado a viver perguntando nos fórums do porque uma variável ```string``` não está funcionando como ```int```. Isso é básico e deveria estar na mente de qualquer programador. Se você está aprendendo, aprenda isso o quanto antes. É imperativo! Não que você vá programar nessas linguagens, elas são apenas um estímulo para você entender como a programação com códigos reais funcionam.

Abuse de exemplos e de testes de lógica no [pseudocódigo][pseudocodigo]. Quanto mais você praticar, mais será capaz de criar programas reais e que resolvem problemas da vida real. Aliás, desde já saiba: programadores são resolvedores de problemas. Pegamos problemas que todos já desistiram de resolver manualmente e automatizamos a solução, através de código. Coffee in, code out.

Agora imagine, usando a analogia que dei anteriormente, que o pseudocódigo seja a planta de uma casa. Você até pode construir o imóvel sem a planta baixa, mas dificilmente você conseguirá alcançar o melhor e possivelmente pode cometer erros crassos de arquitetura, tentando reinventar a roda em coisas que já foram resolvidas e que poderiam ser utilizadas, se você tivesse estudado a base da construção civil.

---
Continuemos.

Agora tenha em mente os códigos que são usados em produção. Pense neles como a fundação e as paredes da casa. Mas eles não são o suficiente, você também precisa dos paradigmas de programação (podemos dizer que seriam como as colunas e vigas de sustenção). São eles que darão sustentação para que seu código funcione. Você pode escolher entre vários tipos e até mesmo combinar os paradigmas diferentes, só não vai conseguir construir um código sem um.

Todos nós sempre começamos com o [paradigma estruturado][estruturado], com variáveis globais e que podem ser alteradas em qualquer lugar do código. Depois, podemos ir para a [Programação Orientada a Objetos][oo], [Programação Funcional][funcional] ou [algum outro paradigma][paradigmas]. De qualquer forma, você vai escolher um deles.

Você consegue imaginar uma casa sem essas colunas? Eu também não. Certamente caíriam nos dias de chuva e vento forte.

---
Agora pense nas ligações de água e esgoto, eletricidade e comunicações dessa casa. Não tenho dúvidas que a empresa fornecedora desses serviços não sabe como é feita a ligação interna, apenas entrega o serviço próximo ao seu portão e dali para dentro, é SUA responsabilidade fazer chegar nos lugares desejados. 

Posso dizer que a comunicação com o banco de dados também é assim. O DB não deve saber como mostrar os dados armazenados na tela pro usuário, isso é responsabilidade sua. Não importa o quanto você queira, o DB não precisa saber disso. É como se a companhia de água olhasse pra torneira da sua casa e dissesse: "essa torneira não está nos nossos padrões".

Aqui começam a entrar os [ORMs][orm], que são uma camada de abstração para acesso ao banco de dados. Na sua casa, não importa se a energia da tomada está vindo de um fonte solar ou da concessionária: apenas que tem energia com tensão e corrente suficientes. O mesmo se aplica aos bancos de dados; sua aplicação deve ser agnóstica de DB, de forma que se vc precisar trocar, não vai impactar o usuário. Mas isso é assunto para outro artigo.

---
Veja a quantidade de coisas de base que falei, sem mencionar outras coisas básicas, como [memória][memoria], [Design Patterns][patterns], princípios do [SOLID][solid], [algoritmos de busca, seleção e ordenação][busca], [estruturas de dados][estruturas]... Essas são coisas que, muito provavelmente, estão abstraídas no framework que você quer aprender, mas que são essenciais para seu aprendizado e para que seu software/sistema não seja refém do desenvolvedor do framework. Não que eu conheça tudo isso, mas todos os dias busco me aperfeiçoar e conhecer mais sobre esses temas, que são extremamente relevantes. Porém, não recomendo à ninguém estudar o avançado sem conhecer o básico.

## Conclusão

Para concluir, vamos corrigir a analogia inicial. Se aprender a linguagem e suas bases é como construir uma casa do zero, então os frameworks, que tem muitas dessas coisas abstraídas, podem ser comparados a uma construção pré-moldada, onde, como num [Lego][lego], você encaixa os blocos que quer usar e brincar.

Em breve, vou escrever um outro artigo, explicando sobre o que se deve fazer para iniciar a carreira em programação.

[portugol]: http://lite.acad.univali.br/portugol/
[visualg]: http://visualg3.com.br/
[fluxograma]: https://pt.wikipedia.org/wiki/Fluxograma
[pseudocodigo]: https://pt.wikipedia.org/wiki/Pseudoc%C3%B3digo
[estruturado]: https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_estruturada
[oo]: https://pt.wikipedia.org/wiki/Orienta%C3%A7%C3%A3o_a_objetos
[funcional]: https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_funcional
[paradigmas]: https://pt.wikipedia.org/wiki/Paradigma_de_programa%C3%A7%C3%A3o
[orm]: https://pt.wikipedia.org/wiki/Mapeamento_objeto-relacional
[memoria]: https://pt.wikipedia.org/wiki/Mem%C3%B3ria_(inform%C3%A1tica)
[patterns]: https://pt.wikipedia.org/wiki/Padr%C3%A3o_de_projeto_de_software
[solid]: https://pt.wikipedia.org/wiki/SOLID
[busca]: https://pt.wikipedia.org/wiki/Algoritmo_de_busca
[lego]: https://pt.wikipedia.org/wiki/Lego
[php]: https://www.php.net/
[estruturas]: http://calhau.dca.fee.unicamp.br/wiki/images/0/01/EstruturasDados.pdf