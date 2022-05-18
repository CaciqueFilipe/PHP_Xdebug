# Adicionando os breakpoints


- E finalmente chegou a hora da gente realmente debugar, da gente depurar código, entender o que está acontecendo, por onde o nosso código está passando.

- Primeiro, antes de tudo, eu vou rodar esse comando para executar nossos testes unitários e analisar que a gente tem uma falha. Os testes que ordenam os nossos lances estão vindo com erro, alguma coisa está acontecendo. Então, aparentemente, os nossos lances não estão sendo ordenados corretamente.

- Então vamos lá, vamos analisar o que a gente pode fazer aqui para descobrir o que está errado. Eu posso vir aqui no método “Get 3 maiores lances”, e ele só retorna os maiores, então provavelmente o erro não está aqui. Beleza. Vamos lá nesse “avalia”. Aqui está acontecendo bastante coisa. Ele está vendo de todos os lances, ele está pegando o valor e vendo se é maior do que o maior valor. Se for, se o valor do lance atual for maior do que o maior valor atual, ele está salvando o valor do lance atual como maior.

- Já se for menor do que o menor valor atual, ele está salvando. Ok. Aparentemente não é isso que vai ordenar, e aqui tem, avalia os 3 maiores lances. Peguei aqui, ele está pegando todos os lances, está ordenando esses lances baseado em valor, Ok. Ordenou os 2 lances, e depois pegando só os 3. Aparentemente o nosso código está certo.

- Então, como eu já comentei anteriormente, bem no início do treinamento, é muito comum quando a gente está pegando um erro, um bug no código, e a gente colocar “var_dump” para entender o que está acontecendo. Então vamos lá. Eu vou pegar esses lances e adicionar aqui um “var_dump” de lances. E eu vou parar a execução do teste, para eu encerrar aqui, poder analisar com calma. Então vou executar. Beleza, olha. Coloridinho, bem legal. O Xdebug já está ajudando a gente. Então repara que aqui a gente já começa a achar estranho. Eu tenho três lances, eu deveria ter três lances, onde o maior é de 2000, o do meio é de 1500, e o menor é o 1000 reais.

- Aqui, de cara, o primeiro lance já é o de mil reais. O do meio é de 1500, e o últimos, que deveria ser o primeiro, o de 2000. Então a gente está vendo aqui que está invertido. Ok. Vamos ver onde que essa inversão está acontecendo. [02:27] Então vou tirar o “var_dump” daqui, e eu vou acessar esse método aqui. A gente já viu que não é aqui, beleza. Então deixa eu voltar. Vou no “avalia”. Então aqui no “avalia 3 maiores lances” eu vou ter um “var_dump” antes de fazer a ordenação, para ver como é que está.

- Dei um “var_dump”. E aqui está ordenado daquela forma aleatória, e se eu adicionar um “var_dump” depois, então é aqui que está acontecendo. O nosso ordenador, vamos chamar assim, nossa função que ordena, não está funcionando. [03:03] Mas antes da gente continuar, repara que para cada execução eu estou gerando um profiling. Então deixa eu ir lá no nosso arquivo “php.ini” e remover isso aqui. Pronto, não vamos mais gerar profiling porque o PhpStorm está toda vez me avisando que tem arquivo novo sendo gerado.

- Voltando para cá, foco. A nossa função que ordena um lance está errada, mas para a gente chegar até essa conclusão, eu precisei ir dando “var_dump” em vários pontos na aplicação, e aqui, ok, é uma aplicação pequena, mas se fosse uma aplicação maior, poxa, seria interessante a gente ter uma ferramenta um pouco mais profissional de ir andando pelo nosso código. Eu queria, por exemplo, chegar aqui, e verificar qual o valor de “lances”. Para garantir que até esse ponto ele estava correto ou não, mas sem fazer o “var_dump”. Eu quero uma ferramenta mais profissional. E é aí que entra o Xdebug.

- Então, se eu vier aqui e adicionar esse breakpoint, o que quer dizer um breakpoint? Se eu clicar logo aqui do lado do número da linha, e colocar essa bolinha vermelha, e eu voltar lá no meu teste, e eu vir aqui para executar o meu teste, ou seja, no PhpStorm, e aí que entra o ponto de que o PhpStorm é mais interessante para você realizar esse treinamento.

- Eu até vou deixar um exercício para você configurar a funcionalidade que a gente vai ver agora em outros editores, mas com o PhpStorm você não precisa configurar, ele já está pronto.

- Mas voltando, eu vou clicar aqui nessa setinha verde e, debug. Esse é nome desse método. Quando eu executar, olha o que acontece. Ele começou a executar o nosso código e parou, exatamente onde eu coloquei a bolinha. Aqui a gente consegue avaliar todos os valores, todas as variáveis disponíveis atualmente. A gente consegue verificar aquela callstack, igual a gente tem no Xdebug, a gente tem aqui para saber o que foi chamado, em que ordem, o que aconteceu até chegar aqui.

- Então aqui eu dar uma olhada nos meus valores. Eu sei que leilão eu estou chamando “get lances”, então eu tenho aqui os lances, e aqui eu posso analisar, olha só. A ordem deles nesse momento ainda está aquela ordem aleatória. Então até aqui o nosso bug ainda não tinha acontecido.

- Então repara que dessa forma eu não preciso ficar colocando “var_dump”, e o que é pior: é muito comum a gente adicionar um “var_dump” no código para debugar, para descobrir o que está acontecendo, e esquecer ele lá, mandar um código para produção com “var_dump”. Já aconteceu comigo, inclusive, não vou me isentar, e é muito comum, infelizmente, quando a gente faz esse debug de forma não muito profissional.

- Então, utilizar dance artefato é muito mais interessante. Se a gente adiciona isso que é chamado de breakpoint, ou seja, um ponto de quebra, um ponto de parada, a gente consegue interromper a execução do programa e analisar, fazer uma análise do que está acontecendo até aquele ponto.

- Analisei que até aqui o meu array de lance estava correto. Então posso continuar a aplicação porque eu sei que o problema não é até aqui, é depois. Então eu posso clicar nessa setinha verde que simplesmente retorna, retoma a execução do programa. Posso também, como o próprio PhpStorm já me falou, apertar F9. Mas aqui eu vou clicar para continuar a execução.

- Ele continuou. Ele está rodando mais vezes nesse ponto porque tem vários testes. Agora que finalizaram os testes que passam por esse “avalia três maiores lances”, eu posso dar uma olhada aqui no meu console e ver que os testes continuam falhando.

- Então recapitulando o que a gente fez aqui. A gente adicionou um ponto de parada na nossa aplicação, e toda vez que um código passar por aqui, todas as vezes que um código passar por esse método aqui, ele vai parar para a gente poder analisar. Então, de novo, se eu vier e executar utilizando o debug, a gente tem uma fotografia completa do que aconteceu até aqui.

- E no caso, toda vez que ele passar por essa linha, como eu mostrei, toda vez que passar, em todos os testes, em todos os cenários de testes que a gente descreveu, ele vai passar por aqui. Então o que a gente pode fazer caso a gente já tenha analisado, finalizado a nossa análise, eu posso interromper a execução e parar aqui mesmo, que aí o programa não vai continuar rodando.

- A gente já entendeu o que é esse ponto de parada, esse breakpoint, mas eu quero ver o que está acontecendo daqui para frente, eu quero continuar a execução analisando ponto a ponto.

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64542)

