# Votação TAO

{% hint style="info" %}
Votação TAOA TAO está atualmente no processo de proposta, e a demo será submetida a votação do detentor do token no outono.
{% endhint %}

## O início... <a href="#the-beginning..." id="the-beginning..."></a>

Inicialmente Aragon foi gerido centralmente por seus fundadores, **Luis Cuende** e **Jorge Izquierdo** . Com liderança derivada de milhares de horas de investimento em capital, eles delegaram trabalho diretamente a funcionários que entregaram a visão central de liderança em um "[Modelo em cascata](https://pt.wikipedia.org/wiki/Modelo\_em\_cascata)" de governança.

Com o passar do tempo, Aragon mudou para uma estratégia de votação tokenizada que **permitia aos detentores de tokens** a capacidade **de votar nas decisões** da empresa. Os detentores de tokens votam em uma abordagem de [**democracia ponderada**](https://en.wikipedia.org/wiki/Weighted\_voting) em que 50 tokens equivalem a 50 votos, 500 tokens equivalem a 500 votos etc. foi noivado. Talvez uma evolução do [Paradoxo da Votação](https://pt.wikipedia.org/wiki/Paradoxo\_de\_Condorcet) abordada há mais de 200 anos pelo pioneiro da governança [Nicolas de Condorcet](https://pt.wikipedia.org/wiki/Marqu%C3%AAs\_de\_Condorcet) - Aragon (e muitos outros DAOs) redescobriu que, para a maioria das pessoas, o custo de votar sabiamente excede o valor dos resultados.

## A transferência dos Fundos Aragon... <a href="#the-transfer-of-the-aragon-funds..." id="the-transfer-of-the-aragon-funds..."></a>

Para colocar um ponto mais preciso, em maio de 2022, Aragon votou para " [**Transferir os fundos do projeto Aragon para um DAO de Aragon governado pela (delegada) ANT**](https://voice.aragon.org/processes/#/0x21b2ea5345d2e0c941dd44ff4c43fc4683088b846ddb3234d1690b000000000e) **".** Essa decisão envolve a movimentação de centenas de milhões de dólares de um sistema de governança para outro na blockchain Ethereum. De qualquer forma, este é um "grande negócio" e uma **oportunidade espetacular de testemunhar e participar de um processo de governança** que nunca poderia ter sido possível sem acesso ao conjunto de ferramentas blockchain agora disponíveis. E, no entanto, apenas 46 das [13.000 carteiras com tokens votaram,](https://etherscan.io/token/0xa117000000f279d81a1d3cc75430faa017fa5a2e) representando menos de 4% do total de tokens emitidos. Na indústria, isso é muitas vezes referido como "não ideal."™

Não estamos sozinhos em nosso esforço para aumentar o engajamento e melhorar os resultados. Em muitos DAOs, a participação de votos na faixa de 1 a 3% é a norma, e obter um engajamento de 5 a 10% é quase inédito. Uma das vantagens empolgantes dos mecanismos de votação digital é que eles nos permitem a oportunidade de explorar novas abordagens que os produtos tradicionais de caneta e papel nunca poderiam considerar seriamente.

[A Democracia Líquida](https://pt.wikipedia.org/wiki/Democracia\_l%C3%ADquida) é um desses sistemas que foi avançado nas últimas duas décadas por grupos como o [Partido Pirata da Alemanha](https://pt.wikipedia.org/wiki/Partido\_Pirata\_da\_Alemanha) na tentativa de aumentar o engajamento, **permitindo que os usuários deleguem seu poder de voto** a outros usuários temporariamente e para incentivar ou coagir aqueles que foram delegadas autoridade para agir sobre ele - quebrando assim o paradoxo.

> A imagem abaixo mostra um exemplo de voto democrático delegado onde ocorrem várias camadas de delegação. Por exemplo, dois eleitores delegam seus votos a um terceiro eleitor, e então esse eleitor delega todos os três votos sob seu controle para outro delegado que acaba votando em uma decisão ou candidato.

![Um exemplo de voto democrático delegado](../../.gitbook/assets/Delegative\_democracy,\_proxy\_voting,\_liquid\_democracy.png)

Em 2021, a equipe do [Token Engineering Commons](https://tecommons.org/) lançou um painel de configuração [https://config.tecommons.org/config/1](https://config.tecommons.org/config/1) para apoiar seu trabalho no [Conviction Voting](https://medium.com/giveth/conviction-voting-a-novel-continuous-decision-making-alternative-to-governance-aa746cfb9475) - um mecanismo experimental que aproveita algumas das oportunidades técnicas derivadas de ferramentas de votação totalmente digitais, como Aragon. A organização organizou uma série de "Param Parties" que, por sua vez, levaram ao lançamento de um token comunitário.

Com a votação para financiar a governança descentralizada avançando ( [Aprovar 72k para financiar a governança descentralizada S1 (dGov) de 1º de maio a 31 de agosto de 2022.](https://voice.aragon.org/processes/#/0x21b2ea5345d2e0c941dd44ff4c43fc4683088b846ddb3234d1690b0000000008) ), a equipe dGov trabalhou em uma variedade de propostas, incluindo a decisão de trabalhar com os laboratórios Blossom, General Magic para tomar o trabalho que fizeram para a TECommons e entregar um produto e processo semelhante ao da comunidade de Aragon. Financiamento e supervisão foram entregues pelo subDAO executivo com[ comunicação e notas orçamentárias ocorrendo no fórum](https://forum.aragon.org/t/financial-proposal-demoing-a-tao-voting-dao/3622) .

****[**A votação do**](https://token--engineering--commons-gitbook-io.translate.goog/tec-handbook/governance/voting-tools-and-methods/tao-voting?\_x\_tr\_sl=auto&\_x\_tr\_tl=pt&\_x\_tr\_hl=es-419&\_x\_tr\_pto=wapp) **** Tao é uma variação da democracia líquida desenvolvida pelo [Token Engineering Commons](https://tecommons.org/) com um conjunto limitado de parâmetros:

* ​Suporte[ necessário](https://forum.aragon.org/t/tao-voting-support-required/3663) - quanto suporte total é necessário para que uma proposta seja aprovada
* [Quorum](https://forum.aragon.org/t/tao-voting-minimum-quorum/3664) mínimo - porcentagem mínima de suporte de token necessária
* [Duração](https://forum.aragon.org/t/tao-voting-execution-delay/3668) da votação - a duração da votação (geralmente em dias) de uma proposta
* ​Execution[ Delay](https://forum.aragon.org/t/tao-voting-vote-duration/3665) - quantidade de tempo após uma proposta passar para que a execução ocorra
* [​Votação ](https://forum.aragon.org/t/tao-voting-delegated-voting-period/3666)Delegada - este é o período de tempo, dentro da Duração da Votação, em que os delegados podem emitir votos que lhes foram conferidos. Quando este período termina os delegados não podem mais votar.
* ​Quiet[ Ending](https://forum.aragon.org/t/tao-voting-quiet-ending-period-and-quiet-ending-extension/3667) - verifica os resultados invertidos durante a parte final da Duração da votação e adiciona mais tempo de votação em caso de inversão.
* [​Depósito de ](https://forum.aragon.org/t/deposit-and-challenge-deposit/3669)proposta - uma quantia definida de fundos usada como garantia necessária para criar uma proposta
* [​Período de ](https://forum.aragon.org/t/settlement-period/3670)Liquidação - se um indivíduo acredita que uma determinada proposta é maliciosa, contém um erro ou não está alinhada com o Pacto da Comunidade, ele pode [contestar a proposta](https://forum.1hive.org/t/disputable-honey-pot-celeste-and-agreement-user-process/1343).

> Utilizando um dashboard (imagem abaixo) com alguns parâmetros na tela vamos **engajar a comunidade** em uma discussão sobre os valores e riscos associados ao **processo delegado** . Este painel está vinculado a discussões sobre cada parâmetro e serve para nos ajudar a moldar a estrutura de governança de nosso DAO daqui para frente.

![O dashboard com alguns parâmetros na tela era usado para engajar a comunidade.](<../../.gitbook/assets/Screen Shot 2022-08-11 at 10.30.03 PM.png>)

Embora esses parâmetros não pretendam abranger toda a amplitude da possibilidade democrática líquida, eles nos dão um ponto de partida para explorar as oportunidades, riscos, sucessos e fracassos. Esperamos que você trabalhe conosco para esclarecer essas ideias e continuar este trabalho de pesquisa em andamento.​

Existem centenas de ótimos artigos sobre o assunto - aqui estão alguns:

* [A Convergência de Delegações Iterativas na Democracia Líquida em uma Rede Social ](https://arxiv.org/pdf/1904.05775.pdf)-
* [https://en.wikipedia.org/wiki/Liquid\_democracy](https://pt.wikipedia.org/wiki/Democracia\_l%C3%ADquida)

​

> <mark style="color:purple;">**Você tem uma pergunta?Deixe seus comentários aqui nosso fórum Aragon**</mark>** 👇**

{% embed url="https://forum.aragon.org/" %}
