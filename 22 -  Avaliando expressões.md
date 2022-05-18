#  Avaliando expressões

- O que eu quero fazer é: primeiro recapitular o que a gente tem feito até aqui. No capítulo anterior e nesse, a gente está aprendendo a depurar um código, ou seja, eu estou executando, no meu caso aqui, um teste, mas poderia ser muito bem um arquivo comum, como a gente fez no início, mas eu estou aproveitando que nós temos testes, e executando os testes no modo debug do PhpStorm, que utiliza o XDebug.

- Então ao fazer um debug, eu consigo parar num breakpoint, inclusive num breakpoint condicional, para poder analisar o que está acontecendo.

- Aqui eu já vi como navegar pela aplicação, inclusive ir para a próxima linha, e até entrar em uma chamada de função anônima ou método. O que eu quero fazer agora é: em vez de simplesmente analisar os lances, eu quero ver, eu quero avaliar, inclusive deixa eu remover os lances daqui, eu quero avaliar essa expressão aqui, eu quero ver quanto essa conta está me retornando, quanto esse cálculo está me retornando para saber se eu estou retornando um valor negativo, positivo, ou não.

- E para isso a gente pode utilizar esse símbolo aqui, de calculadora, que se chama evaluate expression, ou “avaliar expressão”. Aqui, repara que ele até copiou a parte que eu já tinha selecionado, posso clicar nessa setinha de expandir para a gente ver isso maior, e aqui eu vou definir a expressão que eu quiser, e quando eu clicar em evaluate, ou seja, avaliar, ele vai me dar um resultado aqui. E eu estou vendo que eu estou retornando um inteiro, 500, que é maior do que 0. Ou seja, eu estou dizendo que o lance 2 tem que vir primeiro. E correto, porque o lance 2 é maior nesse caso, o valor do lance 2.

- Então, se eu quiser analisar o valor do lance 2 apenas, eu posso avaliar. Ele me mostra que são 2000. Se eu quiser ver o valor do lance 1, tenho aqui. Se eu quiser ver todo o conteúdo do lance, olha só, ele mostra todo o conteúdo, inclusive o usuário, com o seu nome. Então eu consigo analisar partes do meu código sem continuar a execução.

- Eu posso ver qual o valor do meu leilão. Nessa função anônima eu não tenho o leilão no meu escopo porque eu só tenho lance 1 e lance 2. Mas, se eu fechar isso aqui e pular, sair daqui, voltar para cá. Aqui, perfeito. Se eu vier para cá e tentar avaliar essa expressão, eu consigo, inclusive, ver o valor do meu leilão. Então eu consigo ter todas as informações. A data de início, que é um datetime mutable. Posso pegar esse datetime mutable... Então, “leilão_data_início”, aqui, posso fazer um format com ele, eu posso executar qualquer código em PHP aqui. "m-d" e avaliar a expressão de qualquer código PHP. Isso é muito interessante, isso é muito legal.

- Com isso a gente não precisa de novo ficar fazendo conta de cabeça, a gente não precisa abrir uma calculadora às vezes, ou saber o que um método vai retornar. Eu posso simplesmente executar e garantir que ele está fazendo o que a gente espera. Só aquela porçãozinha do código.

- Já entendemos mais uma funcionalidade interessante, mas e se eu quisesse, por exemplo, fazer o meu teste falhar de propósito, em vez de retornar os três primeiros leilões, retornar só dois.

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64546)
