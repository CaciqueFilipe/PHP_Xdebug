# Watches

- Mas vamos nessa. Queria conversar com vocês sobre o que a gente fez no capítulo anterior, onde a gente ficou depurando o valor de lances, e garantindo que a ordenação dele estava correta. Então vamos lá, executar de novo esse teste aqui com o debug. Ótimo, ele vai parar. E o que a gente fez anteriormente? Pegou os lances, pode pular, entrei aqui sem querer, mas sem problema, é uma linha só. A gente veio aqui em “lances” e analisou. Está ok, está fora de ordem.

- Aí pulou, fez a ordenação, e aí vê de novo aqui, agora está em ordem. Então o que acontece? A gente está analisando o valor da variável “lanches”, correto? A gente está observando essa variável “lances”.

- Então a gente pode fazer exatamente isso: adicionar uma observação nela, ou seja, eu quero ficar observando, eu quero ficar alisando, eu quero ficar dando uma olhada com mais atenção para variável “lances”. Então eu vou adicionar um watch, ou seja, uma verificação, uma observação, em “lances”. E aqui eu consigo analisar de forma separada os meus watches, ou seja, aqui eu tenho todas as variáveis, tudo, todos os valores estão aqui, mas aqui eu tenho uma lista separada do watches, então eu posso analisar os meus lances aqui de forma separada. E aí eu consigo ver que ele está no valor correto ou não.

- Com isso, eu vou iniciar o debug de novo, e repara que o meu watch continua aqui, ou seja, eu continuo observando ele mesmo esse valor não existindo no contexto atual. Mas vamos lá. Vou criar um debug, e olha só, por enquanto não existe lance.

- Então eu pulo essa linha e agora existe. Então repara que eu tenho aqui um ponto específico para analisar o que eu preciso para esse momento de depuração. Então essa aba de watches, que você pode analisar aqui, aqui embaixo, nessa setinha do final, clicar no óculos e você abre a aba de watches, então aqui você pode dar uma atenção especial para a variável, para a propriedade que você quer analisar o momento. Então com isso, a gente pode ver todas as modificações acontecendo aqui.

- “Mas, Vinícius, eu poderia muito bem analisar o valor aqui”. Sim, exatamente. Você poderia. Só que você não teria a visibilidade de lances quando ele não tiver sido definido ainda, e você tem que se contentar de visualizar os lances junto com todas as outras variáveis. Então o interessante do watches é uma visualização separada e exclusiva para o que você está precisando analisar naquele momento, naquela sessão de depuração, vamos chamar assim.

- Agora, outras coisas interessante que seriam legais da gente fazer. Quando a gente estava passando aqui por essa função anônima, eu tive que pegar o valor desse aqui para analisar, peguei o valor desse e depois fiz a soma. Fiz de cabeça, ou numa calculadora, não importa. Eu fiz a conta para saber o resultado que estava dando. Seria interessante eu simplesmente poder pegar isso aqui e executar o código para ver quanto ele está devolvendo.

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64545)
