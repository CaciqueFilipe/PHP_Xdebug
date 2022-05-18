# Gerando o profiling

- E chegou na hora da gente falar de uma funcionalidade muito interessante do XDebug, que é de criar **profiling**. Eu honestamente não sei uma boa tradução para isso, mas basicamente significa durante a execução de algum código, gerar informações do que aconteceu, quando aconteceu e como aconteceu. 

[Link docs profiler](https://xdebug.org/docs/profiler)

> Por exemplo, eu criei aqui o código bem simples, extraí de um teste que a gente tinha e criei um arquivo separado, onde a gente cria uma conexão com o banco de dados qualquer, isso não é importante, e a gente está criando um leilão e salvando esse leilão do banco de dados. Depois a gente está finalizando esse leilão e atualizando ele no banco de dados.

- Então é um programinha relativamente bobo, mas eu quero analisar o que aconteceu, se essa aplicação está demorando muito tempo e o que está demorando muito tempo para poder analisar e realizar melhorias onde for necessário.

- Então vamos lá na documentação do XDebug entender o que é esse tal de profiling. Primeiro, ele já informa que a gente consegue visualizar essas informações com ferramentas externas, e a gente vai falar sobre uma ferramenta externa, uma das possíveis, mas vamos focar na parte de gerar esse arquivo, essas informações.

- A gente pode definir essa configuração aqui, ou seja, profile enable, e sempre que o PHP executar um código PHP, ele já vai gerar esse profile. Então vamos lá. Copiar. Lá no nosso *“php.ini”* eu vou colocar o enable igual a 1. XDebug. Fiz besteira aqui. Então o “profile_enable = 1”.
```
xdebug.profiler_enable=1
```

- E outra coisa que a gente precisa definir é para onde esses arquivos de profiling vão ser salvos. Então vou copiar, colar aqui, e vou definir que isso vai ser salvo em “C:”, deixa eu copiar um caminho daqui. Deixa eu abrir o Git Bash. “$ cd documents/curso-phpunit/curso-3”, “$ mkdir profiling”, “$ cd profiling”. Aqui. Então eu vou pegar desse caminho aqui. Só que eu preciso pegar utilizando corretamente o caminho do Windows, que é “c:” e é utilizando “\”. Então só estou modificando isso aqui para utilizar o caminho correto.
```
xdebug.profiler_output_dir=caminho_do_diretorio
```

- Então basicamente o que eu fiz foi: eu criei uma pasta nova chamada “Profiling” lá no nosso projeto, e dela eu só peguei o caminho, e estou definindo aqui. Como eu não estou habituado a utilizar o Windows, vamos ver se essas contra barras funcionam dessa forma ou não, mas basicamente a gente está definindo o diretório de saída onde vão ser salvos os arquivos de profiling.

- Então agora que a gente habilitou e fez, já definiu onde isso vai ser salvo, vamos executar esse arquivo “PHP atualizar-leilão”. Rodou bem rápido, aparentemente tudo certo. E aqui é um arquivo foi gerado, chamado “cashgrind.out.” o ID do processo do PHP que rodou. Então a cada novo processo que foi executado, um novo arquivo vai ser gerado.

- Beleza. Então a gente tem aqui, e repara que não é um arquivo muito legível, não é um arquivo que a gente conseguiria analisar com muita facilidade. Para isso que a gente precisa de ferramentas externas. Mas antes da gente utilizar uma ferramenta, eu queria comentar com vocês que isso é algo que exige recursos, isso toma tempo. No caso executou bem rápido porque é um programa bem simples, mas num programa real isso levaria um tempo, então não é interessante deixar isso habilitado sempre. Então é legal você habilitar só na hora que for usar, ou se for o caso de uma aplicação web, existe ainda uma outra possibilidade, que é ativar essa configuração “profiler enable trigger”, e sempre que a gente enviar uma requisição e quiser fazer o profile dessa requisição, a gente manda ou através da URL ou através do corpo com post, ou criando um cookie chamado “xdebug_profile”. Se a gente enviar essa informação, aí o XDebug vai criar o profile para a gente.

- No nosso caso eu vou deixar ele habilitado por padrão porque a gente está fazendo os testes aqui pela linha de comando, que é um pouco mais rápido para executar. Mas, no caso de web, é interessante utilizar esse “profiler enable trigger”, ou seja, só habilitar quando eu quiser.

- Voltando aqui. A gente habilitou que o XDebug crie arquivos de profiling, e disse para ele onde a gente quer que esses arquivos de profiling sejam salvos. Ótimo. Agora está na hora de a gente analisar isso, certo? E para isso a gente vai utilizar uma das ferramentas que ele recomenda. Aqui ele recomenda algumas. Ele recomenda para o Linux o KCacheGrind, ele recomenda no Windows esse QCacheGrind, ou WinCacheGrind. Enfim, existem algumas opções. Mas eu vou utilizar uma solução para web, chamada de Webgrind.

- Então eu já tenho aqui o Git Hub dela. É essa ferramenta que a gente vai utilizar para analisar o profiling gerado.

**Para conhecer o processo com mais detalhes e algumas outras configurações, você pode conferir os seguintes links:**

https://www.jetbrains.com/help/phpstorm/enabling-profiling-with-xdebug.html

https://xdebug.org/docs/profiler

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64540)


