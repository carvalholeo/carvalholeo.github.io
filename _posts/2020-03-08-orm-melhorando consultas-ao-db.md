---
layout: post-ads
title:  "ORM: melhorando o jeito que você consulta seu banco de dados"
categories: [ 'Por onde começar' ]
image: assets/images/mapa.webp
author: leo
tags: [ programacao, dicas, iniciantes, linguagens, frameworks, featured, orm ]
---
No artigo anterior dessa série, em que falei sobre [a importância de aprender a linguagem antes do framework][framework], fiz uma analogia sobre como a companhia de luz entrega energia na residência. Partindo disso, quero falar hoje sobre o que é um ORM e sua importância para o desenvolvimento de software.

Então, pegando o exemplo dado naquele artigo, pensemos um pouco. A empresa de energia não sabe quantas tomadas tem no imóvel que vai entregar o ponto de eletricida; não sabe quantas ou onde estão as lâmpadas; não faz a menor ideia sobre os equipamentos que vão consumir energia naquele lugar. A responsabilidade dela é apenas instalar os fios no seu poste particular, entregar a tensão (voltagem) contratada, fornecer energia nos padrões aceitáveis segundo a legislação local e realizar a medição de consumo para posterior cobrança da utilização. Nada mais.

Por outro lado, você também não tem noção de onde vem toda a energia consumida; não precisa saber quais são as matrizes energéticas até sua residência; não se preocupa com o tipo de fiação de alta tensão externa; pouco importa para você se tem uma subestação exclusiva para sua cidade ou se ela é compartilhada com outras. A sua responsabilidade é apenas instalar uma fiação adequada à legislação local, colocar pontos elétricos suficientes e bem dimensionados para o imóvel, instalar dispositivos de proteção contra raios e sobrecarga e fazer o pagamento pela utilização do serviço. Nada mais.

*"Mas Léo, o que esse papo tem haver ORMs e programação??"*

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/vSy-U2MUuOA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>

Simples. As responsabilidades são bem dividas e claras.

Numa aplicação real, você com certeza precisa consultar dados em algum lugar. Em quase 100% dos casos, eles estão em um banco de dados, cujo informações pode ser consultadas através de SQL.

O problema que se apresenta é que, para os iniciantes, é complicado ter de aprender mais uma linguagem, apenas para fazer um [CRUD][crud]. Ou seja, além de pensar em aprender como criar uma aplicação, ainda que simples, o dev iniciante precisa aprender onde esses dados estão armazenados e como consultar ou criar novas informações no banco de dados. E é aí que entram os ORMs.

ORM é uma sigla que significa *"Object Relational Mapping"*, ou "Mapeamento de Relação-Objeto". Com os ORMs, você não precisa criar uma query SQL para fazer um CRUD simples na aplicação. Basta continuar utilizando sua linguagem de programação favorita, com alguns comandos específicos de framework ou lib, que, por baixo dos panos, criam uma query SQL. Esta query é, em grandiosa parte das vezes, a mais otimizada possível.

Bem, se é um mapeamento, então temos uma espécie de "tradução". Então, vamos os termos originais e seus correspondentes.

<div class="table-responsive">
    <table class="table table-bordered table-hover table-sm">
        <thead>
            <tr>
                <th scope="col">SQL (Relação)</th>
                <th scope="col">ORM (Objeto)</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Tabelas</td>
                <td>Classes</td>
            </tr>
            <tr>
                <td>Linhas (registros ou tuplas)</td>
                <td>Instâncias</td>
            </tr>
        </tbody>
    </table>
</div>

Assim, ao invés de trabalhar com uma string ou um array que vem como resposta do banco de dados, você utiliza instâncias de objetos da sua própria aplicação, que pode trazer as regras de tipos e objetos para os dados que serão utilizados. Além disso, como dito anteriormente, não precisa se preocupar com os comandos SQL utilizados; apenas com as classes e suas instâncias.

-----
Apenas falar é fácil. Vou dar um exemplo usando o Eloquent, o ORM padrão do Laravel. Como o objetivo desse post não é configurar uma aplicação do zero, vou desconsiderar essa parte. Visualize apenas o jeito de fazer as coisas. Para isso, vamos considerar uma tabela chamada "Clientes" e como inserir dados nela.

-----

No SQL:
```sql
INSERT INTO 'usuarios' ('nome', 'cpf', 'email', 'usuario', 'senha', 'esta_ativo') VALUES ('Chapolin Colorado', '12345678901', 'chapolin@colorado.com', 'chapolin', 'minha-astucia', 1);
```

No PHP, com Eloquent:

```php
$usuario = new Usuario();

$usuario->nome = "Chapolin Colorado";
$usuario->cpf = "12345678901";
$usuario->email = "chapolin@colorado.com";
$usuario->usuario = "chapolin";
$usuario->senha = "minha-astucia";
$usuario->esta_ativo = 1;

$usuario->save();
```

O código acima faz com que você continue trabalhando com o código no paradigma orientado a objetos, sem acrescentar a complexidade de aprender outra linguagem. Apesar da simplicidade do SQL, não é interessante parar de aprender algo para aprender outro.

Tanto o exemplo em SQL quanto com Eloquent, vai gerar o mesmo resultado: salvar um registro no banco de dados, com as informações do Chapolin Colorado.

Dessa forma, além de diminuir a barreira de entrada no mundo da programação, isolamos as responsabilidades e mantemos o código o mais limpo possível.

É claro que nesse artigo não tenho a intenção de esgotar o assunto que, por si só daria uma série de tutoriais e explicações (talvez o faça no futuro). Mas estou abertos a feedbacks sobre esse assunto e como melhorar esse artigo :-)


[framework]: http://localhost:4000/preciso-realmente-aprender-linguagem-antes-framework/
[crud]: http://devfuria.com.br/sql/mysql-crud/