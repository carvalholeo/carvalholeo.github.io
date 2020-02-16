---
layout: post-ads
title:  "Você tem certeza que está seguro na internet?"
categories: [ segurança, séries ]
image: assets/images/cadeados.jpg
author: leo
tags: [ sticky, featured, dicas, autenticação, dois fatores, lgpd, senhas, vazamentos ]
---
Já parou para pensar na quantidade de apps e sites em que você é cadastrado? Em quantos lugares você preenche um formulário para acessar as informações? Já pensou em como deve ser a estrutura desse banco de dados e se ele está criptografado? E se, de repente, esse cadastro fosse vazado e suas informações expostas?

Pois saiba que essa é uma coisa extremamente corriqueira. É mais fácil você ter suas informações vazadas do que ganhar na loteria ou um raio te acertar. Isso acontece porque muitas empresas não levam a sério segurança da informação, o que leva a ter seus dados e informações pessoais sob constante risco. E com a [LGPD][lgpd] prestes a entrar em vigor, é mais do que necessário que você pense em seus projetos com [segurança e privacidade desde o começo][privacy-by-design], como *feature* padrão.

Neste artigo, no foco não é no desenvolvimento de software, mas sim nos SEUS dados e como você cuida deles (se é que cuida).

## Senhas iguais para todos os sites

Já contou quantos sites ou apps você tem cadastro? Eu já. Somente de sites e apps, são mais 250. Não, você não leu errado. São mais de DUZENTOS E CINQUENTA sites/apps cadastrados. Fora as senhas dos cartões (e eventualmente senhas específicas de Internet Banking ou caixa eletrônico).

Sejamos francos: todos nós já deixamos senhas iguais. Não conheço ninguém que tenha capacidade plena de administrar tanta senha diferente. Pelo menos, quando eram senhas iguais para todos os sites, não faziam parte da [lista das 100 senhas mais fracas do mundo][senhas-fracas].

Preocupado com isso, passei a utilizar um gerenciador de senhas, o [LastPass][lastpass]. Com ele, eu tenho uma senha diferente para cada um dos sites em que estou cadastrado. Quando aparece a tela de login dele, o app faz o preenchimento automático. Dá para colocar segurança adicional em senhas específicas (como senhas de banco e e-mails principais de recuperação). Na web, tem extensões para diversos navegadores, que permite o mesmo comportamento. E quando você precisa de uma senha nova, ele pode criar uma nova automagicamente.

Desde o Android 8, há uma [opção nativa para gerar e gerenciar as senhas][senhas-android]. Além desses dois, há outros gerenciadores de senha, que são multiplataforma:

 * [Dashlane][dashlane]
 * [Keeper][keeper]
 * [1Password][onepassword]

Em todos eles, há uma coisa em comum: você precisa lembrar apenas da senha mestra (a que abre o seu cofre de senhas). Todas as outras, você pode esquecer (literalmente). E claro, ter uma senha mestra forte é ESSENCIAL. O Tecnoblog fez uma [matéria comparando][materia-tecnoblog] os gerenciadores de senhas.


## Será que seus dados já vazaram?

Ok, você talvez esteja pensando que estou sendo alarmista ou algo do genêro. Com as recentes notícias de vazamento (e as notícias de vazamento constante do Facebook), pode ser que você não saiba se seu e-mail ou nome de usuário estão no meio da lista da vazados. Para isso, apresento-lhes o ["Have I been pwned?"][haveibeenpwned]. É um serviço gratuito que você pode colocar seu e-mail e confirmar se ele está em alguma lista de vazamentos que o site teve acesso.

No mesmo site, você pode cadastrar seu e-mail, para receber alertas quando seu e-mail aparecer em alguma lista de vazamento, com o correspondente local de origem do vazamento (espero que não tenha nada). Também, pode verificar se alguma das senhas que você utiliza saiu em uma das listas.

Nem só de Facebook o mercado de vazamentos sobrevive. De acordo com o site, já tiveram dados vazados Adobe, Atlas Quantum (BRASIL-SIL-SIL-SIL), Avast, Badoo, Dropbox e outros. Você pode encontrar aqui a [lista completa][empresas-vazadas] de sites que tiveram dados vazados (e quais dados foram vazados) e quando o incidente ocorreu. Recomendo uma visita. Sério.

Uma técnica bacana que você pode usar para saber onde ocorreu o vazamento (ou se alguém vendeu seus dados sem seu consentimento), é o uso de um alias. Isso pode ser feito de forma fácil e automática no Gmail. Basta fazer colocar o sinal de + após seu usuario, junto com uma identificação, desta forma:

```meu.usuario + siteQualquer@gmail.com```

Quando qualquer plataforma for te mandar um e-mail, você recebe normalmente, junto com esse identificador. Se o seu e-mail for vazado junto com esse alias, já sabe a origem do vazamento e a quem recorrer (administrativa ou judicialmente).

Para acabar essa seção: se você quer confirmar que o seu usuário não está tentando utilizar uma senha que já foi vazada, você pode olhar a [documentação da API aqui][api-vazamento] e ver como fazer essa integração com sua plataforma.


## Autenticação de dois fatores

Apesar de recomendar isso com muita força, eu não tenho a ilusão de que as pessoas sigam isso. Inclusive, é uma das coisas que podem ajudar a evitar invasões às suas contas nos diversos serviços que você utiliza.

Com a autenticação de dois fatores (também chamado de autenticação de dois passos, two-factor authentication ou 2FA), ao fazer login na sua conta, você só consegue acessá-la após digitar um código temporário ou responder uma pergunta de segurança. Isso protege seu login, evitando que alguém que teve acesso ao seu e-mail e senha possam entrar e ver suas informações pessoais.

Como existem alguns tipos de 2FA, vou falar de cada um separadamente.

### Tipos de 2FA

#### Código temporário por SMS

Por muitos anos, foi utilizado o celular como ponto de autenticação secundária para sites e apps. Isso se popularizou demais quando o Facebook trouxe o [AccountKit][accountkit], que abstraia a complexidade de mandar SMS para o usuário, sem precisar se preocupar com a necessidade de contratar um provedor de serviços ou com estes custos.

No entanto, esta técnica tem uma falha: o [SIM Swap][simswap]. Esta é uma brecha de segurança em que o agente malicioso, com a ajuda de alguém de dentro da operadora ou de posse dos seus documentos, consegue trocar o seu número de chip. Assim, o atacante pode entrar em serviços com senhas vazadas (seções anteriores) e receber um código temporário por SMS. Este ataque, embora não seja tão simples (visto que você precisa de alguém de dentro da operadora ou ter seus documentos em mãos), quando executado com sucesso pode te levar a perder seu WhatsApp ou ter [problemas com o Twitter][twitter-jackdorsey], como foi o caso do CEO da plataforma, Jack Dorsey.

Conclusão: EVITE USAR ESSE MÉTODO, SEMPRE QUE POSSÍVEL. Ponto final.


#### Perguntas de segurança

Nesta técnica, você escolhe algumas perguntas de segurança e em seguida preenche as respostas. Evite isso, também, porquê as respostas podem ser utilizadas como recurso para Engenharia Social (e posteriormente usados para comprar produtos ou serviços em outros locais).

Se for absolutamente inviável usar 2FA sem Perguntas de Segurança, como no caso da Apple, no lugar das respostas, NÃO COLOQUE AS RESPOSTAS VERDADEIRAS. Use uma string aleatória (pode ser uma gerada pelo gerenciador de senhas). Assim, dá para evitar problemas maiores no futuro.


#### Cartão de segurança/Grade de dados

Aqui, você tem um cartão com algumas senhas (lembro de usar isso há alguns anos no Banco Bradesco) ou um papel com uma grade (usei essa técnica no LastPass por um tempo).

A parte boa é que aquela grade é exclusivamente sua e é SUA responsabilidade cuidar desta folha/cartão. A parte ruim é que se você perder e não tiver um fallback, pode perder acesso completo à sua conta. Também, se você usar todas as combinações possíveis, é necessário conseguir um novo antes de fazer alguma nova operação, seja ela no banco ou em qualquer outro serviço.


#### Senhas adicionais

Esta técnica é muito utilizada em bancos, onde você tem uma senha para entrar no internet banking, uma senha para o cartão, uma senha para caixa eletrônico e uma senha adicional para autorizar transações na internet (Caixa, estou falando de você).

Ela é eficaz, porquê somente você tem acesso à essa senha (espero que isso seja verdade para você), e as transações somente são autorizadas se você digitar essa senha adicional, protegendo sua conta de fraudes.

Na nossa vida digital, você pode usar [2FA de senha adicional no WhatsApp][senha-whatsapp] (faça isso, por favor, para seu próprio bem).


#### Aplicativos de códigos OTP

Esse é o meu favorito. Por meio dele, você cadastra sua conta em um app (lista abaixo), que gera um código OTP (One-time padding), que dura apenas 30 segundos. Passado esse tempo, é gerado um novo código, completamente diferente do anterior.

Na configuração dessa opção no serviço, como Facebook, Gmail, Amazon, Registro.br e outros, você escaneia um QR Code e digita o código inicial no serviço, para sincronizar. Depois disso, seu smartphone não precisa estar conectado à internet para gerar o código, isso é feito offline!

O cuidado que você precisa ter aqui é: CONFIGURE UM FALLBACK! Isso garante que, se você perder acesso ao smartphone, ainda possa entrar no serviço sem maiores dificuldades.

Se você possui uma conta Microsoft, recomendo que use a opção da Microsoft como app OTP para todos os outros serviços. Se não, pode usar qualquer um da lista indistintamente.

 * [Microsoft Authenticator][msauth]
 * [Google Authenticator][googleauth]
 * [LastPass Authenticator][lastpassauth]
 * [Authy][authy]

---
Por fim, já falei por cima, reforço aqui: UTILIZEM UM FALLBACK. Fallback pode ser uma ligação, verificação por SMS, código por e-mail, códigos prévios que ficam na sua máquina/smartphone, senha adicional... Tenham alguma coisa, para evitar que você perca acesso à sua conta, sofrendo de lock-out.

## Estou seguro?

A resposta é simples e rápida: não. Pelo menos, não 100%. Assim, você precisa tomar cuidado com suas informações, dados pessoais, afim de mitigar a maior quantidade possível de problemas que podem ocorrer.

Lembre-se de usar criptografia em suas aplicações (MD5 e SHA-1 não podem mais ser consideradas criptografias). Garanta que os dados dos seus usuários estão seguros e que se você sofrer algum tipo de ataque/vazamento, eles não serão prejudicados.

Este é um assunto extenso e não é o objetivo desse artigo esgotar o assunto, visto que isso é quase impossível. É um alerta para que você não sofra.

[lgpd]: http://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/L13709compilado.htm
[privacy-by-design]: https://beytech.com.br/2019/04/20/lgpd-7-pontos-para-entender-a-nova-lei-de-protecao-de-dados-no-brasil/

[senhas-fracas]: https://www.teamsid.com/1-50-worst-passwords-2019/
[lastpass]: https://www.lastpass.com/pt/how-lastpass-works
[senhas-android]: https://www.techtudo.com.br/dicas-e-tutoriais/2018/05/android-8-oreo-como-usar-o-preenchimento-automatico-de-senhas.ghtml
[onepassword]: https://agilebits.com/onepassword
[dashlane]: https://www.dashlane.com/pt/
[keeper]: https://www.keepersecurity.com/pt_BR/
[materia-tecnoblog]: https://tecnoblog.net/192790/gerenciador-senhas-por-que-usar/

[haveibeenpwned]: https://haveibeenpwned.com/
[empresas-vazadas]: https://haveibeenpwned.com/PwnedWebsites
[api-vazamento]: https://haveibeenpwned.com/API/v3

[accountkit]: https://www.accountkit.com/
[simswap]: https://gizmodo.uol.com.br/sim-swap-tecnica-clona-whatsapp/
[twitter-jackdorsey]: https://epocanegocios.globo.com/Empresa/noticia/2019/08/jack-dorsey-ceo-do-twitter-teve-sua-propria-conta-hackeada-na-rede-social.html
[senha-whatsapp]: https://faq.whatsapp.com/pt_br/android/26000021/
[msauth]: https://www.microsoft.com/pt-br/account/authenticator
[googleauth]: https://support.google.com/accounts/answer/1066447?co=GENIE.Platform%3DAndroid&hl=pt-BR
[lastpassauth]: https://lastpass.com/auth/
[authy]: https://authy.com/