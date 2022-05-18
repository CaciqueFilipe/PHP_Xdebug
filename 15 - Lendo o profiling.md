# Lendo o profiling

- Então agora a gente já entendeu o que é informações de profiling, e a gente já gerou um arquivo de profiling aqui. Ótimo. Então, o que a gente quer fazer agora é ler, analisar esses dados de profiling.

- Então, utilizando o webgrind, a gente vai ler esse arquivo. Então a primeira coisa é vir aqui e clonar esse repositório ou fazer o download do zip. Fazendo o download do Zip, você vai extrair na pasta que quiser, e eu já fiz isso aqui, eu já extrai.

- Então agora, utilizando o terminal, você vai acessar a pasta que você acabou de extrair. E nela, a gente vai executar o comando **“composer serve”**. E isso vai fazer o quê? Vai levantar um servidor web PHP onde a gente vai conseguir analisar, onde a gente vai conseguir acessar a interface do webgrind.

- Então vamos lá, acessar *“localhost: 8080”*, e aqui a gente já tem a interface do webgrind. Então ele vai dizer: “Selecione um arquivo acima”. Então a gente pode vir aqui e selecionar algum, e a gente vai selecionar esse primeiro aqui. E repara que ele já mostra sobre qual script que esse arquivo de profiling está falando. E no caso a gente está vendo um que foi sobre atualizar leilão.

- Então eu vou clicar nele, e update. E aqui a gente tem uma informação, bastante informação sobre tudo o que aconteceu. E repara que o nosso arquivo é bem pequeno, a gente tem pouquíssima coisa, mas aqui, o webgrind já está mostrando para a gente que bastante coisa aconteceu.

- E aqui nós temos algumas informações. A primeira coluna mostra se é uma classe, um método de uma classe, se é um código procedural, ou se é uma função interna do PHP. E aqui nós temos o gráfico do que foi mais utilizado. Se foi mais utilizado funções internas, include, require, ou seja, trazer arquivos externos. Classes e métodos, ou funções procedurais. E aqui a gente consegue ver que no nosso código tem mais classes e métodos do que funções procedurais, do que funções internas, e também mais do que include e require.

- A gente já sabe o que é, e aqui nós temos a chamada do método em si. E se a gente clicar, por exemplo, nessa setinha, ele mostra em que contexto ele foi chamado e o que ele fez, o que ele chamou. Então mostra que ele chamou a função prepare do PDO, depois executou um PDO statement. Criou um novo leilão. Enfim, ele mostra tudo o que aconteceu, e quanto cada parte consumiu de recurso.

- E aqui, logo do lado, a gente consegue analisar esse arquivo, o código-fonte em si, nessa parte que a gente está analisando, que a gente está realmente analisando, vendo o que aconteceu.

- Então aqui a gente consegue ver o arquivo. Aqui nós temos o número de vezes que essa função, que esse método foi chamado. Então repara que no nosso exemplo, a função mais chamada foi a bind value, do PDO statement. Ou seja, a gente está utilizando bastante SQL.

- Aqui a gente consegue ordenar pelo total, pelo tempo que cada função levou para ser executada, e aqui a gente ainda tem o total inclusivo, ou seja, da função e tudo que ela fez para executar. Então no caso, obviamente, a main, o arquivo principal, é o que levou mais tempo porque ele que executa tudo. Mas se a gente quiser ver individualmente quanto cada função levou em microssegundos, que foi o que a gente definiu aqui, a gente pode ordenar dessa forma.

- E aqui a gente tem, pelo menos para mim, uma surpresa. O que mais demora para ser executado não é o SQL, a gente não está demorando mais tempo para executar, por exemplo aqui, um SQL. A gente está demorando bastante tempo para pegar o autoloader do composer. Então aqui a gente já identificaria um gargalo de performance, e poderia gerar esse autoloader de forma otimizada, que existe um comando no autoloader que a gente otimiza. Existe um comando no composer que a gente otimiza o autoloader.

- Então aqui a gente já saberia qual parte atacar se nossa aplicação tivesse lenta. E ainda existe uma outra funcionalidade interessante que eu não vou cobrir nesse vídeo, nesse treinamento, mas que seria um gráfico das chamadas de funções. Seria algo parecido com um fluxograma. Mas para executar isso, a gente precisaria configurar outras bibliotecas, o que levaria um tempinho, então eu não vou cobrir isso nesse treinamento.

- Mas basicamente, recapitulando o que a gente fez, foi configurar para que o Xdebug gere um arquivo de profiling, e a gente definiu onde ele vai gerar esse arquivo. A gente baixou o webgrind, e o webgrind já consegue ler essa informação aqui para saber de onde buscar os arquivos. Então, quando a gente acessa o webgrind, ele já mostra aqui os arquivos que a gente pode analisar o profiling.

- Então, quando a gente analisou, definiu o que é exibir 100% dos dados e em microssegundos. A gente poderia ver em percentual, por exemplo. Acho que no caso eu derrubei o servidor. Deixa eu subir o servidor de novo. Se eu atualizar aqui, vamos ver se ele já voltou a funcionar. Ok. Se eu tentar exibir isso em porcentagem, ele mostra o percentual de que cada função demorou para executar, e não microssegundos, que talvez, no nosso caso, como são valores muito pequenos, pode ficar confuso. Aqui a gente tem um percentual de quanto cada função levou. Repara que o main leva quase 100% do tempo, porque é tudo, obviamente.

- Mais uma vez a gente pegou e criou um arquivo de profiling, um arquivo com informações do que aconteceu, e conseguiu analisar utilizando o webgrind. E agora a gente sabe que se a gente quisesse otimizar a nossa aplicação, hoje, o ponto mais crítico é o autoloader do composer.

- Ótimo, a gente já entendeu o que é o Xdebug, como ele pode melhorar o “var_dump”, como colocar cores na linha de comando, por exemplo. A gente viu como ele ajuda a gente a visualizar os erros, a gente viu a pilha de execução, a gente viu aqui como fazer profiling, como analisar o que está acontecendo à saúde da nossa aplicação. Mas, o ponto principal do Xdebug, que é a característica, o carro-chefe dele, é realizar debug, é depurar aplicações.

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64541)

