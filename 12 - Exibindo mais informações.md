# Exibindo mais informações

- Então, como eu falei, a gente consegue pegar informações adicionais na hora de analisar a **call stack**, ou seja, a pilha de chamadas.

- Uma dessas informações possíveis para a gente analisar são as superglobais, ou seja, os dados que vem do servidor. E a gente pode habilitar através dessa configuração. Então vamos lá. Primeiro eu vou habilitar essa configuração, e eu vou definir como 1. Na verdade é como on, ou seja, ativado. Ativei para ele cuspir as variáveis globais. Vamos ver o que acontece simplesmente adicionando essa opção, sem nada mais.
```
xdebug.dump_globals=on
```

- Quando eu atualizo, repara que ele não mostra nada para a gente. Então, junto com a opção de exibir as variáveis globais, a gente precisa também informar o que a gente quer exibir. Então vamos lá. Por exemplo, aqui. De SERVER. Eu vou fazer exatamente igual ao que está no exemplo. De SERVER, eu quero pegar o request e URI, ou seja, a URL da requisição.
```
xdebug.dump_SERVER=REQUEST_URI
```

- Então vou interromper, subir de novo, e quando eu executo agora, eu tenho acesso aos dados, a request e o URI que a gente recebeu. E aqui, a gente não está conseguindo ver todas as strings completas. Por quê? Porque a gente definiu aqui como 5, que o número máximo de informações de uma string vai ser de 5 caracteres. Então eu posso remover essa configuração que a gente tinha adicionado anteriormente.
```
xdebug.var_display_max_data=5
```

- Interrompi o servidor, subi de novo. E agora que eu tirei o limite de caracteres, eu vejo que a URL é **“/erro.php”**. Então com isso a gente pode analisar mais informações, a gente pode adicionar, por exemplo, se eu quiser trazer os dados do método, então “request method”. Em vez da URL, eu quero trazer qual o método foi utilizado, qual o verbo HTTP foi utilizado nessa requisição. Posso vir aqui que ele vai exibir que foi utilizado o verbo get.
```
xdebug.dump_SERVER=REQUEST_METHOD
```

- Agora, se eu quiser exibir todos os dados do server, por exemplo, eu posso vir aqui e em vez de colocar um específico ou dois, também é possível, eu posso vir aqui e colocar um asterisco. Dessa forma, eu estou informando que eu quero pegar todos os valores da superglobal server, ou seja, tudo o que tiver nessa variável, eu vou trazer.
```
xdebug.dump_SERVER=*
```

- Então atualizo e tem lá, todas as informações. Isso às vezes pode acabar trazendo informação desnecessária, coisa que a gente nem precisa. **Por isso que é interessante a gente configurar só para o que fizer**. 

> Isso, obviamente, a gente pode utilizar direto no nosso código, utilizando _“ini.set”_. Então, por exemplo, se eu quiser pegar os dados de uma requisição que foram passadas por get, eu posso pegar “xdebug.dump.get” e eu vou passar o asterisco, ou seja, eu quero pegar todas as informações que foram passadas através do verbo get.

- Então aqui eu vou remover, porque eu não quero mais exibir os dados da variável server. Vou reiniciar o servidor. E com isso eu tenho aqui todos os dados da variável get, que no caso está vazio. Se eu passar algo aqui, eu vou receber que “get algo” tem um valor aqui. Então assim eu consigo pegar todos os dados de uma superglobal.

- Mas eu não consigo fazer só isso. Se você analisar, a gente tem a opção ainda de exibir as variáveis locais também. Então eu posso exibir quais eram as variáveis disponíveis aqui no contexto, aqui nesse escopo, quando o erro foi lançado. Então, por exemplo, a gente vai ver qual era o valor de último lance nesse caso. Então eu posso configurar exatamente igual no exemplo utilizado “show local vars”.
```
xdebug.show_local_vars=on
```

> Então vamos ver. “xdebug.showlocalvars = on”, e vamos ver se só isso já resolve, já exibe para a gente. Reiniciei o servidor, e agora, quando eu exibo, tem lá. O lance, que é o nosso parâmetro que a gente está recebendo, ele é um objeto do tipo, que tem um usuário, que tem um valor.

- E o último lance a gente tem aqui um lance que tem usuário, e a gente consegue analisar que nesse lance que a gente passou por parâmetro, é um lance que tem um usuário com a referência dele, o ID desse usuário, o código que identifica ele, é 4. E esse outro usuário aqui, que já tinha do último lance, também é 4. Ou seja, é o mesmo usuário.

- Se a gente quisesse conferir com os valores, eu poderia aumentar aqui a profundidade máxima do que exibir de dados de 1 para 2. E agora, reiniciando o servidor, eu tenho inclusive o nome sendo exibido. Dessa forma eu tenho certeza do que está acontecendo, tenho certeza de que essa propriedade “usuário” está sendo refletido, e por isso o meu erro está acontecendo.

- Então, de novo. Existem vantagens e desvantagens com essa abordagem. A vantagem é: obviamente nós temos todas as informações aqui na cara, eu não preciso ir passando no código para entender. Mas a desvantagem é que nós temos muita informação sendo jogada na nossa cara. Às vezes nem tudo é necessário, então cabe a gente configurar e colocar só o que faz sentido porque é necessário para o nosso caso.

- Ainda existem outras configurações que a gente pode analisar, como, por exemplo, se vão exibir essas informações em todos os erros que aconteceram, que o Xdebug exibir, ou se vai exibir só no primeiro, aquelas variáveis superglobais, se vão exibir os dados que não estão definidos também. Os dados da variável server, por exemplo, que não que não foram preenchidos, se também seria exibido na nossa tela.

- Então tem muita configuração para a gente analisar, e você clicando em cada uma, ele te leva para uma página de todas as configurações explicando cada uma. Vale muito a pena dar uma conferida, vale a pena ler sobre isso para entender melhor as formas que o Xdebug informa para gente o que está acontecendo.

- Agora a gente já tratou bastante sobre os erros, sobre essa funcionalidade do Xdebug. Primeiro a gente entendeu o que ele é, para que serve. A gente viu que ele ajuda com o “var_dump”, ele ajuda bastante. Nós entendemos as configurações dele, a gente viu que dá para configurar. E aqui tem uma página com todas as configurações. A gente viu como ele pode ajudar a gente com os erros, para a gente encontrar, depurar os erros. Só que o Xdebug, como eu falei, tem várias funcionalidades. E uma muito interessante é analisar tudo o que aconteceu na sua aplicação, inclusive para você entender o que é gargalo de performance. O que está demorando ser executado na sua aplicação etc.

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64539)
