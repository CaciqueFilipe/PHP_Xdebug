# Caminhando pela aplicação

- Agora que a gente já entendeu o que é um breakpoint, esse ponto de pausa, esse ponto de parada, a gente não quer simplesmente parar aqui e analisar e pronto, parar a aplicação. Eu quero poder continuar executando e analisando passo a passo.

- Vou iniciar o debug desse meu teste de novo, e vamos lá. Vou criar um debug. Ok. Tem aqui um debug. E o que a gente estava fazendo é: tonalizando esse leilão, vejo os lances dele, ok, e depois encerro a aplicação. E não é isso que eu quero fazer. Eu quero analisar depois de executar essa linha.

- Então eu tenho a opção de, que é o nome, step over, ou seja, pula essa linha e continua analisando. Anda uma linha no método atual, na linha de execução atual, e continua analisando. Então, se eu fizer isso, se eu clicar nessa linha, agora ele executou, o PhpStorm, o PHP executou essa linha, passeou, fez tudo o que tinha que fazer, e agora eu consigo inclusive analisar essa variável “lances”.

- Agora a gente vai estar nessa próxima linha, então eu quero ver o que está acontecendo aqui dentro para saber o que está errado. Então eu vou clicar no mesmo botão, certo? Cliquei e ele pulou a execução, e repara que os meus lances já estão aqui ordenados de forma crescente. Não é como a gente quer, a gente quer de forma decrescente.

- Ok, mas por que será que ele não entrou aqui? O step over funciona exatamente dessa forma. Ele não vai entrar nas chamadas de método, como por exemplo aqui em “get lances”. Ele não entrou no método “get lances” para analisar tudo lá. E também não entrou nessa função anônima que a gente definiu. Ou seja, ele passa direto, só pelas chamadas do método atual. Sem nenhuma função anônima, sem método, sem nada disso. Só do método atual, no arquivo atual.

- E não é isso que a gente quer. Então eu vou parar aqui e iniciar uma outra sessão de debug. Vou clicar aqui e vamos nessa. Agora, o que a gente vai fazer? Eu vou pular essa linha, porque eu não quero entrar em “get lances”. Mas agora eu não quero pular, eu não quero executar essa linha e ir direto para a próxima desse arquivo. Eu quero ir para a próxima linha, que é a função anônima, que é essa função aqui, que faz ordenação.

- Então eu posso utilizar essa outra opção, que é “step into”. Quando eu selecionar esse “step into”, ele vai entrar na função desejada, vai entrar no método desejado, vai entrar na função anônima desejada, e a gente pode continuar analisando. Aqui a gente consegue verificar que eu tenho lance 1 e lance 2, e eu sei que a função anônima passada para o usort funciona dessa forma.

- Eu preciso devolver um número negativo se o primeiro item for vir antes no array do que o segundo item. Eu vou retornar a zero se eles forem iguais, e eu vou retornar o número maior do que 0 se o lance 2 tiver que vir primeiro nesse array. E eu sei que eu preciso retornar um número que faça o maior lance vir primeiro. Então vamos ver se isso está acontecendo.

- Eu tenho aqui o lance 1, que são 1000 reais, e o lance 2, 1500. Então estou retornando 1000 reais, que é do lance 1, menos 1500, que é do lance 2. Ou seja, eu estou retornando um valor negativo. Isso está fazendo com que lance 1, que é de mil reais, venha primeiro no array. E eu não quero. Ou seja, eu preciso devolver nesse caso um número maior do que 1.

- Então, o que eu posso fazer aqui? Em vez de tirar do lance 1 o valor do lance 2, eu vou tirar do valor do lance 2 o valor do lance 1. Agora sim a nossa aplicação deve funcionar. Então eu posso continuar executando aqui, ou eu posso parar para executar sem esse breakpoint, porque agora eu confio que o método está certo.

- Então eu venho aqui e vou executar sem debug. Nosso teste passou. Então esse é um processo de depuração, esse é um processo de debug. A gente vai analisar, a gente vai parar onde tem que parar, entender o que está acontecendo, e a partir disso tomar as decisões, como foi a decisão que eu tomei agora.

- A gente ainda consegue fazer algumas outras coisas interessantes, a gente consegue navegar um pouco mais pela aplicação, e eu vou mostrar agora. Se eu executar isso aqui de novo, com debug, ele parou. E agora eu quero entrar no método "get lances”, então eu vou utilizar o “step into”.

- Entrei aqui. Agora, supondo que eu tenho vários métodos, várias linhas aqui para serem executadas, mas eu não quero mais continuar nesse método, eu já quero voltar para o método que chamou ele para a função, para o código, para a linha de código que chamou esse método, eu posso utilizar aqui o “step out”, ou seja, sai da execução desse método e volta para a linha padrão que eu só quero analisar lá naquele outro método.

- Ele voltou. Se eu fizer de outra forma, por exemplo, vou executar aqui, parou. Se eu continuar, “step into”, ou seja, entra lá, e continua o “step into”. Nesse caso vai funcionar exatamente igual. Agora, se eu tivesse uma outra linha aqui, deixa eu parar, como por exemplo uma definição de variável “A = 1”, eu vou executar esse debug de novo. Se eu fizer o “step into” e continuo navegando, ele vai continuar nesse método, ele vai continuar nesse método até chegar no final.

- Agora, se eu não quiser fazer isso, se eu quiser já sair e partir para a execução no método original, eu posso clicar no “step into”, e aqui, eu não quero que ele continue executando e depurando parte a parte, eu quero voltar lá para o método original, “step out”. Ele já voltou aqui, executou, obviamente o método “get lances”, fez o que tinha que fazer, mas ele não precisou ficar alisando, passando linha por linha lá.

- Esses são os mais importantes, e são os comandos que você mais vai utilizar. “Step over”, ou seja, pula para a próxima linha da linha de execução atual. “Step into”, que é entrar em cada uma das chamadas e executa com fluxo natural, com fluxo real do programa. E o “step out”. Ou seja, volta para a linha de execução anterior, volta para o método que chama o método atual, volta para a linha de código que chamou a função atual.

- E isso é interessante para a gente voltar, porque não quer mais analisar, viu que aquele método ali não é aonde a gente quer resolver o problema. Então dessa forma a gente consegue navegar e caminhar pela aplicação, a gente consegue entender passo a passo do que está acontecendo.

- Mas repara que eu acabei executando o método errado de testes. Eu executei aqui um método que deve retornar os maiores lances disponíveis. Só que a gente estava testando inicialmente, o que deve ordenar só os 3 lances, ou seja um leilão que tenha 3 lances.

- Então seria interessante para eu ter reparado, me atentado a isso, se eu conseguisse informar: “Olha só, Xdebug, você só vai parar aqui se ‘lances’ estiver 3, se essa variável ‘lances’ for um array com 3 posições, se eu tiver três lances”. 

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64543)
