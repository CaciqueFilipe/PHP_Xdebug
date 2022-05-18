# Conhecendo o var_dump

- E nesse teste ele acessa um leilão down, ou seja, um objeto que busca, salva, faz o que tiver que fazer em questão de persistência utilizando leilões. Criou um leilão down, salva alguns leilões, e depois recupera os leilões não finalizados. E depois só garante que o leilão não finalizado é o correto, ele está buscando de forma correta.

- Então, se eu executar o teste, qual é o comando para executar? Vou executar 
```
vendor\bin\phpunity
```
> que é aquele arquivo de executar os testes, só que eu vou filtrar para executar apenas esse teste aqui, que é o nome do método de teste que a gente quer executar.

- Quando eu executo, a gente está recebendo uma falha aqui, a gente está em 3 asserts, em três verificações que ele fez, essa aqui falhou. Nessa verificação ele tentou achar variantes 0KM, mas na verdade, o leilão que ele achou foi para Fiat 147 0km. 

> Então o nosso teste está falhando por algum motivo. E é muito comum a gente pegar um código que a gente acabou de escrever ou já escreveu há algum tempo que deveria funcionar e a gente não sabe o que está acontecendo.

- Então a gente começa a tentar encontrar o bug, esse é o processo de depuração, ou de debug, que é para encontrar o problema e entender o que está acontecendo. 

> Então, uma das ferramentas que o PHP fornece é uma função chamada “var_dump”. Esse “var_dump” entrega para a gente o conteúdo de uma variável e o seu tipo, e entrega, cospe na tela de uma forma que a gente consegue visualizar toda a estrutura.

- Ele é um pouco mais interessante que o “Eco”, por exemplo, porque o “Eco” só exibe um dado com o seu valor. Então, por exemplo, a gente não consegue dar “Eco” num array, a gente não consegue exibir todos os valores do array utilizando o “Eco”. Então o “var_dump” ajuda nesse caso.

- Então a gente vai começar a entender o que está acontecendo. Vamos ver o que está vindo aqui em “leilões”, qual conteúdo está vindo em “leilões”. Então eu posso utilizar “var_dump” e passo leilões por parâmetro. Isso vai fazer com que o conteúdo dessa variável “leilões” seja cuspida na tela.

- Então, se eu executar aquele mesmo comando, eu tenho aqui toda a estrutura desse nosso array de leilões. E aqui, repara, que ele já mostra que é um array que contém um item. Beleza, tem um array de 1 item dos nossos leilões. Até aí parece tudo certo.

- No índice 0 desse array eu tenho um objeto do tipo “leilão”. Ok, é o que a gente espera. Esse leilão não tem nenhum lance. Beleza, esse objeto está sendo definido dessa forma, e aqui a gente vê que a descrição é “Fiat 147”. Poxa, estranho. Não é esse que a gente está esperando. A gente está a variante, que foi o objeto que a gente montou, foi o objeto que a gente definiu aqui em “leilões” como a variante não finalizada.

- E o Fiat 147, repara, a gente finalizou ele. E aqui, a propriedade “finalizado”, está vindo como verdadeiro. Então o nosso método buscar, recuperar não finalizados, está, na verdade, me devolvendo os leilões finalizados. Então a gente já entendeu aí que tem algum problema acontecendo.

- Então a gente pode vir entendendo o que o método faz, então se eu acessar “recuperar não finalizados”, ele chama o outro método, “recuperar leilões”, se “finalizado =” a true, e isso deveria ser false. Agora, se eu executar, eu tenho um teste passando. Posso remover aquele var_dump se eu quiser, mas antes eu vou dar uma conferida aqui no que ele exibiu, e eu tenho a variante 0KM “finalizado = false”. Ótimo, exatamente o que a gente esperava.

- Essa função var_dump é muito útil, e a gente usa bastante no dia a dia. não é a forma mais profissional de debugar, de depurar um código, e a gente vai conversar sobre formas mais profissionais e mais interessantes, mas é uma mão na roda e a gente usa bastante no dia a dia.

- Só que isso na web, quando a gente está programando para uma página HTML, por exemplo, utilizar o var_dump pode ser um pouco mais difícil de visualizar. Então vou criar o arquivo aqui só para você entender como que ele ficaria. Eu vou criar um “var_dump.php”. Só um arquivo comum. E nesse arquivo eu vou fazer o require do nosso autoloader. “Vendor autoload”. E aqui eu vou criar um novo usuário. “Usuário = nenhum”. E aqui eu só passo o nome, que vai ser Vinícius Dias, o meu nome.

- E aqui eu vou dar um “var_dump” nesse usuário. Só que agora imagina que isso tudo está numa página HTML. Criei uma página HTML aqui, e no PhpStorm é só digitar o sinal de exclamação e dar tab que ele já faz isso tudo para a gente.
> Então eu vou trazer isso para cá, fechar aqui, e aqui eu abro o PHP, aqui eu fecho o PHP. Não é interessante a gente misturar código PHP com HTML, obviamente, mas eu só estou fazendo isso aqui para dar um exemplo de como fica o “var_dump” lá na web, numa página da web.

- Beleza. Então eu tenho aqui, vou clicar com o botão direito, abrir no navegador, e eu vou abrir no meu navegador padrão, que aqui é o Chrome. Repara que ele mostra tudo numa linha só. Lá no terminal, cada propriedade estava numa linha, separado. Aqui o nosso usuário só tem uma propriedade, que é o nome, mas se fosse um leilão, por exemplo, teriam várias propriedades todas aqui na mesma linha.

- Deixa eu criar um leilão para você entender melhor. “New Leilão”, e aqui “Fiat 147 0KM”. E agora, eu dando “var_dump” nesse leilão, olha só, fica muito difícil de visualizar. Então um truque, de novo, isso não é muito profissional, mas um truque para resolver esse problema de visualização é adicionar aqui no “var_dump”, o “var_dump” consegue mostrar o valor de várias variáveis. Eu não preciso passar uma só. Eu posso passar usuário 1, usuário 2. Eu poderia passar várias variáveis aqui separadas por vírgula.

- Mas o que eu vou fazer é passar uma string. E essa tag, HTML, que eu estou passando aqui para o “var_dump” analisar, faz com que o código seja formatado exatamente como ele é jogado na tela para HTML. Se eu apertar “control+u”, que mostra o código-fonte, o PHP até gera cada propriedade numa linha. Só que o HTML não interpreta essa quebra de linha. Utilizando a tag “pré”, ele vai interpretar.

- Então, se a gente olhar agora, a gente consegue visualizar um pouquinho melhor, um pouco mais parecido com que a gente tinha lá no terminal. Com isso a gente já entende como começar um processo de depuração, de investigar o que tem, qual o tipo de uma variável e todos os seus valores de um objeto, por exemplo. Mas como eu falei mais uma vez, isso ainda não está muito profissional. Então vamos começar a utilizar uma ferramenta bem, molhando o pezinho só nesse oceano que a gente vai ver sobre o Xdebug. Então no próximo vídeo a gente já vai fazer a instalação dele.

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64532)
