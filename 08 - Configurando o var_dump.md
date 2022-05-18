# Configurando o var_dump

[link das configurações](https://xdebug.org/docs/develop#display)

- A primeira que eu queria comentar é sobre a exibição das cores no terminal. Como eu falei, se você estiver utilizando o Linux, talvez você já até tenha visto essas cores acontecendo. E dando uma olhada na documentação, no caso de utilizar Windows, a gente precisar instalar essa ferramenta a mais. Ou a gente pode também utilizar como padrão, como definição dessa configuração aqui, o valor 2.
```
xdebug.cli_color=2
```
- Com esse valor 2, ela vai exibir, o Xdebug vai tentar exibir esses caracteres coloridos, mas dependendo da configuração do seu terminal, da versão, dependendo de algumas coisas do próprio Windows, alguns caracteres estranhos podem ser exibidos.

- Então o recomendado é instalar essa ferramenta, mas no meu caso eu vou definir essa configuração com o valor 2. Então eu vou abrir o meu Xdebug, meu **“php.ini”**, 2. Vou parar isso aqui. E agora eu vou executar na linha de comando o meu “var_dump”. E repara que agora eu tenho a minha linha de comando colorida.


- Eu tinha comentando que eu ia utilizar o Git Bash, mas ele seria útil, seria interessante, se a gente tivesse instalado essa ferramenta, de [XX-ininteligível-XX]. Como eu vou preferir utilizar essa configuração do 2, eu não vou nem precisar continuar com o Git Bash, eu posso voltar para o prompt de comando normal. E aqui a gente tem em negrito, colorido, vem um pouco mais bem definido.

- E existem algumas outras configurações que a gente pode fazer. Se, por exemplo, quando der um “var_dump”, eu só quero ver os filhos diretos, eu não quero ver, por exemplo, as propriedades de date time mutable se eu não quisesse ver os filhos dos filhos, os netos do meu objeto, por exemplo. Aqui em “leilão” tem um filho, seria “data início”, e “data início” tem um date, que é um filho.

- E nesse caso aqui, na estrutura do “var_dump”, é chamado de filho. Mas e objetos ou propriedades? Eu não quero exibir as propriedades das propriedades do leilão. Eu posso configurar isso através de display max children. Então isso controla a quantidade dos filhos de um array, dos arrays aninhados, ou as propriedades dos objetos, quantas são exibidos.
```
xdebug.var_display_max_children=2
```
- Então eu vou colocar isso aqui como 1 e ver o que acontece, porque o padrão é 128. O padrão é bem alto, mas eu vou definir como 1. E ver como que ele vai se comportar. Vou subir o nosso servidor de novo para ver no navegador, que fica um pouco melhor, e olha só, ele só mostra uma propriedade, ele não mostra os restantes.

- Se eu vou colocar 2, ele só vai mostrar duas propriedades. Então com isso a gente consegue limitar quantas propriedades a gente vai exibir. Mas ainda existem algumas outras, como por exemplo, aquela que eu falei de eu não querer ver os netos, vamos chamar assim, as propriedades das propriedades. Eu posso utilizar o display max depth.
```
xdebug.var_display_max_depth=1
```

- Mas vamos lá. Eu quero exibir só em profundidade um nível. Então vou interromper o servidor, subir o servidor de novo, e ele vai mostrar, deixa eu apagar esse max children, vou deixar ele mostrar todos os filhos, todas as propriedades, mas com a profundidade de apenas um nível.

- Vou reiniciar o servidor, que eu sempre me esqueço. E olha lá, ele exibe todas as minhas propriedades com os seus tipos, mas não exibe as propriedades das propriedades, ou os valores dos arrays, que são minhas propriedades. Então ele mantém a profundidade controlada.

- Existem ainda outras configurações, como por exemplo, se eu quiser exibição só os cinco primeiros caracteres de uma string? Eu posso utilizar o display max data, ou seja, controla o tamanho máximo de uma string que é exibida em uma variável.

```
xdebug.var_display_max_data=5
```

- Então vou colocar aqui só um valor bem pequeno, por exemplo, 5. Vou interromper o nosso servidor, vou limpar a tela, subir e o servidor. Isso é importante, a gente sempre tendo que reiniciar o servidor, porque nós estamos editando o arquivo de configurações do PHP. Esse arquivo é lindo assim que o PHP é executado. E aqui o PHP está sendo executado uma vez para subir o servidor. Por isso que a gente sempre tem que reiniciar o servidor.

> E vamos nessa. Quando eu exibo aqui, repara que ele só vai exibir os cinco primeiros caracteres. Só os cinco primeiros caracteres da string. Então a gente consegue controlar quantos e quais dados são exibidos utilizando “var_dump” através das configurações. Isso é bastante útil. Mas, para mim, na minha opinião, o mais útil é colocar as cores do “var_dump”. Isso ajuda bastante quando a gente está desenvolvendo uma aplicação no terminal, no prompt de comando, e está utilizando o “var_dump”, porque visualizar tudo de uma cor só não é tão intuitivo quanto a gente visualizar aqui, utilizando negrito, cores separadas, cores diferentes. Então isso, para mim, a CLI Colors é o principal.

## Então vamos recapitular

- Porque a gente viu bastante coisa nesse capítulo. Primeiro, utilizando o arquivo “php.ini”, do próprio PHP, a gente consegue definir várias configurações para o Xdebug. Algumas dessas configurações permitem que a gente tenha um controle mais interessante sobre os erros que acontecem na nossa aplicação. O force display errors vai garantir que os erros são exibidos independente da configuração do display erros PHP em si.

- E, da mesma forma, a função force error reporting, do Xdebug, faz com que a gente ignore e error reporting do PHP e sobrescreva essa funcionalidade, essa configuração.

- O halt level vai informar para o PHP em qual tipo de erro ele vai simplesmente parar a execução, e não continuar. Que por padrão, é só quando acontece um erro, realmente, não um warning ou um notice. No nosso caso, sempre que acontecer um notice, a gente está parando a aplicação.

- E sempre que a gente utilizar aquele arroba, o operador de supressão de erro, ou controle de erro, a gente está dizendo para o Xdebug que ele vai ignorar esse operador e gritar o erro mesmo assim.

- Aqui, a gente começou a falar sobre o “var_dump”, sobre as configurações possíveis para o “var_dump”, e a gente consegue fazer com que, na CLI, ou seja, no terminal, no command line interface, a gente consiga utilizar cores também.

- No Linux, você simplesmente colocaria esse valor como 1 e as cores já estariam lá. Mas no Windows você tem a opção de instalar uma ferramenta a mais ou utilizar a opção 2, que às vezes pode acabar imprimindo alguns caracteres estranhos, dependendo do seu terminal, diversões etc, mas que no geral vai fazer com que apareçam as cores.

- A gente consegue controlar o nível de profundidade dos dados a serem exibidos, quantos caracteres de uma string vai ser exibido com o “var_dump”, então a gente tem um controle bem interessante. E várias outras configurações estão disponíveis aqui.

- E aqui tem alguns exemplos demonstrando só 2 filhos, mostrando como 16 de tamanho do dado, profundidade de 2, várias configurações ao mesmo tempo. Então ali têm alguns exemplos, e as propriedades, as configurações disponíveis aqui.

- Então é bem interessante a documentação do Xdebug. É tranquila de entender, vale a pena dar uma conferida. Agora que a gente já entendeu como fazer os erros aparecerem, como configurar o “var_dump”, vamos começar a analisar o que ele traz de informação sobre os erros. Mas a gente vai falar sobre isso no próximo capítulo.


- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64536)
