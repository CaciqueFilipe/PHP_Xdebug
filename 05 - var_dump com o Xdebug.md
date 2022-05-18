# var_dump com o Xdebug

## _Vamos começar a conversar sobre as funcionalidades do XDebug._

- Então eu vou voltar aqui para a página principal dele, e aqui ele já diz que é uma extensão do PHP para ajudar no debug e no desenvolvimento. Contém um depurador, um debuger de passo único, e a gente entrar em detalhes do que é isso, mas a gente já viu aqui que pode utilizar com ideias, e é por isso que eu vou utilizar o PhpStorm nesse treinamento.

- E ele também fala que o XDebug faz um upgrade, ele dá esteroides para função var_dump. Ou seja, ele adiciona funcionalidades, ele modifica a funcionalidade da função var_dump. Então vamos voltar para aquele nosso arquivo, deixa eu até parar esse servidor aqui, vamos voltar para esse nosso arquivo var_dump, vou dar “control+z” aqui para voltar para aquele conteúdo antigo, onde a gente mostra o leilão. Deixa até eu renomear essa variável, “shift+f6”, “leilão”. E se você se lembra bem, a visualização estava prejudicada, e eu precisei desse pré aqui.

- Vou remover o pré, porque agora a gente está com o XDebug e ele tem uma facilidade interessante. Vou mais uma vez abrir no navegador, meu navegador padrão, e repara aqui, aqui está com aquela visualização antiga. Agora eu vou subir o servidor web, “php –s localhost:8080”, e eu vou colocar lado a lado, “/var_dump”. Olha a diferença. Aqui é sem o XDebug, que é com aquele servidor que o PhpStorm já tinha subido, que não tinha um XDebug ainda, e aqui é um servidor que a gente acabou de levantar, onde o XDebug já está configurado.

- Então repara a diferença na legibilidade, na leitura, como ele já traz uma facilidade de cara para gente. Ele já mostra aqui que eu tenho o leilão, onde o hash do objeto – não precisa se atentar a isso –, é 3, e aqui ele mostra de forma um pouco mais amigável.

- As propriedades, ele mostra de forma muito mais legível. Eu tenho aqui “lances”, que é privado, está um array vazio, tamanho 0, ótimo. Descrição, que é uma string, e aqui eu tenho conteúdo, e aí ele já mostra o tamanho dessa string aqui, olha só como demora. Até a gente encontrar o string 12 é bem complicadinho. Aqui um booleano, que é falso, põe finalizado. A data de início é um datetime mutable, ele já mostra separadinho cada uma das propriedades. Enfim, a gente já começa de cara, sem configurar nada no XDebug, só por ter instalado ele, a gente já ganha um var_dump mais bonitinho, um var_dump mais interessante.

- E se a gente executar esse mesmo código, deixa eu remover essa parte de HTML, se a gente... Na verdade eu vou remover essa parte de HTML sim para a gente executar esse mesmo código utilizando a linha de comando. Então vou parar aqui, “php var_dump”.

- E repara que aqui ele não atrapalha de forma nenhuma, pelo contrário, ele também deixa isso de forma um pouco mais legível. Se você estiver utilizando um terminal Linux, por exemplo, você vai ver que agora está coloridinho, está bem mais interessante.

- Inclusive, para os próximos vídeos, eu vou começar a utilizar um outro terminal chamado Git Bash. Então caso você esteja no Windows, pode utilizar esse terminal aqui, Git Bash, é fácil de instalar, para que para você possa visualizar melhor a saída dos comandos.

- Então eu vou entrar aqui em “documentos”, “curso php unity”, “curso 3” e executar o var_dump. Então aqui a gente tem uma saída mais interessante. Mas a principal vantagem acontece aqui na web, onde a gente normalmente trabalha a maior parte do tempo utilizando o PHP.

- De novo, se você estiver utilizando o Linux, você vai ver essas saídas coloridinhas, e no próximo capítulo a gente vai começar a conversar sobre essas configurações, sobre deixar colorido ou não, sobre utilizar HTML aqui para fazer o var_dump ficar bonitinho ou não, como a gente pode configurar o XDebug.

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64534)
