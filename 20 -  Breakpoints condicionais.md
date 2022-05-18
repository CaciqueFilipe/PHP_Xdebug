#  Breakpoints condicionais

- Então vamos, antes de qualquer coisa, remover aquela linha inútil que eu adicionei. Posso fechar isso aqui. E vamos lá. Eu vou executar mais uma vez essa chamada do método errado, que é o que deve retornar os maiores lances disponíveis. Só que como não é esse método que eu quero testar, que eu quero debugar, aqui nesse breakpoint, nesse ponto de parada, eu quero informar: “Olha, para aqui, mas só se ‘leilão get lances’”, ou seja, só se nesse leilão eu tiver 3 lances disponíveis.

- Então vamos lá. Eu vou clicar com o botão direito nesse breakpoint, e eu posso adicionar aqui uma condição. Que condição? “leilão get lances” se o count disso é igual a 3. E aqui eu posso escrever código PhpStorm, normal. Inclusive o PhpStorm me ajuda com autocomplete. Isso é muito maneiro.

- Então vamos lá, clicar em done. E agora, olha, ele tem uma interrogação indicando que isso é um breakpoint condicional, ou seja, existe uma condição para ele parar nesse ponto de parada.

- Então se executar aqui, agora, onde eu só tenho dois lances... Vou parar a execução, o debug atual e rodar de novo. E, olha, repara que ele não parou em nenhum breakpoint. Agora, se eu executar esse aqui, onde eu tenho três lances, ele vai parar. Perfeito.

- Esse breakpoint condicional é muito interessante quando, por exemplo, a gente tem um loop, e a gente só quer parar numa condição específica do loop, numa iteração. Imagina que eu tenho 100 lances aqui, e eu estou percorrendo esse lance, e eu só quero parar quando ele chegar no lance para Fiat 147. Se eu tivesse que adicionar um breakpoint no loop sem colocar nenhuma condição, ele passaria por todas as iterações do loop, eu teria que ficar clicando aqui em step into, ou step over o tempo todo até chegar na iteração que eu quero. Com breakpoints condicionais eu consigo definir quando eu quero parar, especificamente. Isso é bastante útil.

- Agora que a gente já está com o gostinho do que é debugar, o que é depurar uma aplicação, vamos ver quais são alguns outros recursos interessantes que o XDebug, junto com o PhpStorm, trazerem para a gente.


- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64544)
