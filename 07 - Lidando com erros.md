# Lidando com erros

- Queria falar sobre algumas outras funcionalidades do Xdebug que são bem legais, e uma, que na minha opinião é uma das mais interessantes antes dos **breakpoints** e debug em si, é uma forma mais interessante de tratar os erros. 

> Porque o PHP tem algumas configurações disponíveis, inclusive eu já vou pedir para você deixar aberto o seu arquivo _“php.ini”_, que foi onde a gente adicionou isso aqui, essa linha que o Xdebug pediu.

- E nesse arquivo _“php.ini”_ existem várias configurações que a gente pode definir para o PHP. E dessa forma a gente consegue personalizar como o PHP vai executar determinadas partes da aplicação. E uma dessas configurações, deixa eu até ver se aqui está definido, é display erros. Isso aqui, de exibir os erros.

- No meu caso está habilitado para exibir os erros. Então vou criar um código aqui que gera um erro para você ver o que acontece. Se eu tentar acessar uma variável que não existe, por exemplo, eu vou tentar dar um _“var_dump”_ em uma variável que não existe, e eu vou acessar, primeiro, através daquele servidor do PhpStorm, que ainda não tinha o Xdebug, e aqui ele mostra para a gente um notice, só gera um aviso que a gente está tentando acessar uma variável que não existe.

- E depois mostra que é null. Porque, por padrão, quando o PHP não acha uma variável, ele parte do princípio que é nula. Agora eu vou abrir esse mesmo arquivo utilizando aquele nosso servidor web que está levantado utilizando o 
``` _“PHP -S localhost: 8080”_ 
```

- Acessei. E olha só a diferença na exibição do erro. O Xdebug já mostra para a gente um erro com muito mais informação, inclusive quanta memória estava utilizando, quanto tempo levou, em que linha, em qual função isso aconteceu um erro. Ele já mostra muito mais informações.

- Agora, se eu ver aqui e desativar os erros, e isso não é uma configuração do Xdebug, é do PHP em si. Se eu desabilitar a exibição dos erros, e eu tentar executar de novo, deixa eu reiniciar o servidor web, e agora, olha só, ele não mostra mais os erros. Isso é muito comum, principalmente em um ambiente de produção, os erros não são exibidos por padrão, porque a gente não quer dar esse tipo de detalhes caso aconteça um erro na nossa aplicação.

- Só que se a gente tiver em um ambiente de desenvolvimento, e essa configuração de exibir os erros estiver desabilitada, isso pode prejudicar a gente. Então a gente pode fazer uso dessa configuração aqui do Xdebug, forçar a exibição dos erros. E eu passo ir lá no meu _“php.ini”_ e adicionar esse valor que, de qualquer forma, deixa um reiniciar aqui, que habilitado ou desabilitado os erros, ele vai forçar a exibição.

- Isso pode ser interessante em alguns casos. Existem alguns servidores que a gente utiliza, principalmente em ambiente de desenvolvimento, onde a gente não pode sobrescrever algumas opções, algumas configurações do _“php.ini”_, porque você provavelmente está se perguntando: 

> “Vinícius, ao invés de adicionar essa linha, eu poderia simplesmente vir aqui e mudar de off para on. Certo?”. E no nosso caso, sim, é a mesma coisa, não faz diferença. Mas em alguns casos, em alguns servidores, a gente não pode sobrescrever as configurações. Mas a gente pode criar novas, e é para isso que essa do Xdebug existe.

- Existem algumas outras configurações sobre erro como, por exemplo, error reporting. Essa configuração informa para o PHP quais erros, qual o nível de erro que ele deve reportar, qual o nível de erro ele deve passar a exibir. Então aqui ele já mostra algumas opções, e no nosso caso está configurado para exibir todos os tipos de erro. Seja notice, warning, um aviso strict, que são algumas configurações de alguns tipos mais restritos, comparações, a forma como a gente está escrevendo, enfim.

- Independente do tipo de erro, a gente exibe todos. Eu posso mudar para, por exemplo, a reportar só a partir de warning. Somente. E agora, se eu reiniciar o servidor, repara que o nosso erro não é mais exibido porque aquele é um notice. Só que eu posso utilizar, mais uma vez, o Xdebug para fazer um “xdebug force error reporting”. E eu posso mudar para exibir todos os erros.

- Então, de novo, parando e reiniciando o servidor, quando eu atualizo, ele ignora aquela configuração inicial. Então, exatamente igual a gente fez com o display erros, tem o error reporting.

> O que significa? Se eu tenho um servidor onde eu não posso sobrescrever uma configuração, eu crio uma nova do Xdebug.

- “Tá, Vinícius, essas configurações que a gente sobrescreve, para mim, no meu ambiente, não é muito útil. Existe alguma que eu possa realmente utilizar?”. 

> E aí vem a próxima configuração, que eu acho bastante interessante, que é a **“halt level”**. O que isso quer dizer? Em qual nível de erro, de problema que vai acontecer, para o PHP parar de executar? Porque se você reparar, ele está exibindo um notice com todas as informações, em qual linha aconteceu o notice qual função etc, só que ele está continuando a execução. Ele está executando e está exibindo o _“var_dump null”_. Então, por exemplo, se eu der um “Eco” aqui, teste, esse teste vai ser exibido. Olha aqui. Ou seja, a execução do script não está parando, ele não está interrompendo nesse erro aqui.

- Agora, se eu quiser fazer com que o PHP pare quando eu encontrar um notice, eu posso utilizar o **“xdebug halt level”**. E eu posso dizer que quando eu encontrar um notice, ou qualquer coisa pior do que um notice, ele vai parar a execução.

- Então eu vou parar os servidores, subir de novo, e agora, quando eu atualizar, repara que ele para. No momento que aconteceu o notice, ele não executa mais nada, ele não exibe mais. Nem aquele “var_dump” e nem o “Eco”.

- Então com isso a gente consegue interromper a execução para garantir que a gente não vai ignorar nenhum notice, que o nosso programa não vai continuar funcionando quando eu receber uma espécie de alerta de um erro que teoricamente não é tão crítico. Mas, se a gente está recebendo esse tipo de aviso, é porque alguma coisa está errada na nossa aplicação. Então isso é muito interessante.

> Outra coisa muito útil é: se você não conhece esse operador, meus parabéns, você não deveria conhecer. Mas se você conhece, existe um operador que é muito utilizado juntamente com essa função de e-mail, e é o operador arroba.

- Quando a gente adicionar o arroba na frente de qualquer função, de qualquer código PHP, ele vai suprimir os erros, ou seja, ele não vai exibir qualquer erro que essa função venha a reportar. O que isso quer dizer? Se a minha função mail der algum erro, não consegui enviar esse e-mail, se eu utilizar o arroba, ela não vai exibir nenhum notice, nenhum warning, nada. Ela não exibe erro.

- Então isso aqui é utilizado quando a gente quer mascarar algum problema na nossa aplicação. E com o Xdebug a gente pode simplesmente colocar **“xdebug screen”**, e a gente pode ver aqui, onde a gente tem o valor padrão como 0, mas se a gente definir como 1, a gente vai fazer com que todos os códigos, mesmo que tenha um operador arroba, de supressão de erro, esses códigos ainda vão emitir os erros.

- Então, por exemplo, se eu tivesse uma variável, que é um array, e tentasse exibir um array como um valor que não existe nesse array, isso vai me gerar um notice, ou seja, vai parar meu script de acordo com essa configuração. Vai parar.

- Se eu adicionasse esse arroba, ele ignoraria esse notice e continuaria executando, mas como a gente definiu que ele vai gritar os erros, ele vai continuar, olha só, na linha 7. Esse “offset 0” não foi definido na linha 7, “offset não definido”.

- Então isso é uma configuração que eu sempre deixo ativada, porque se alguém está utilizando o operador de supressão de erro, algum problema está sendo mascarado no nosso código. Esse operador é algo que a gente não deve utilizar. Isso é algo que a gente deve evitar a todo custo, então o Xdebug permite desmascarar esses problemas, que às vezes as pessoas tentam jogar para debaixo dos tapetes.

- A gente já entendeu que existem configurações a serem feitas com o Xdebug, e a gente já viu que o “var_dump” é muito ajudado quando a gente utiliza o Xdebug.

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64535)
