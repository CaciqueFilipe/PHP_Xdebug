# Configurando o ambiente

- E nos dois últimos capítulos a gente já entendeu bastante sobre depuração, a gente já viu sobre breakpoints, navegar pela aplicação, alguns recursos bem legais que o XDebug e o PhpStorm trazem para a gente, mas surgiu aquela dúvida: e se eu não estiver executando o meu script, o meu código, o meu programa pela linha de comando, pelo PhpStorm? Se eu estiver executando pelo navegador? Se eu vier aqui e acessar essa URL? Como eu vou fazer o debug, a depuração, nesse caso?

- Isso é o que o XDebug chama de remote debbuging, ou debug remoto, depuração remota. Porque, o que está acontecendo? Existe um servidor web rodando, esse servidor web, que vai receber uma requisição, precisa informar algum cliente XDebug, que no caso pode ser vários, e a gente está utilizando aqui o PhpStorm. Então o servidor precisa informar o cliente do XDebug que uma sessão de depuração vai começar, uma conexão de depuração vai começar. E aí o navegador vai parar, e o cliente do XDebug, no nosso caso o PhpStorm, vai abrir no ponto que a gente definiu para o breakpoint, por exemplo.

- Então como que a gente configura isso tudo? A gente tem uma configuração chamada remote enable, do XDebug, e a gente vai definir como 1. Eu já coloquei aqui, então “remote enable = 1”. Dessa forma a gente está habilitando o debug remoto no nosso servidor, no caso com o XDebug.
```
xdebug.remote enable = 1
```

- A gente ainda poderia definir o host, ou seja, a URL, o domínio, o host que vai poder ter essa conexão remoto, que por padrão é o local host, e já é o que a gente está utilizando. E com a porta que o XDebug vai utilizar para se comunicar com a IDE, que por padrão é **9000**, e a gente vai ver o que fazer com esse valor.

- Com isso configurado, a gente precisa de um jeito de fazer o navegador, o servidor, comunicar o cliente, ou seja, o Chrome comunicar o PhpStorm que uma sessão de debug começou. Para isso a gente pode definir variáveis de ambiente etc, ou a gente pode utilizar alguns helpers, umas extensões, e para a maioria dos navegadores existem as extensões, e eu já instalei aqui para o Chrome, que é essa daqui, “XDebug Helper”.

- Com a extensão habilitada eu posso vir aqui e habilitar o modo debug, e agora vamos configurar o cliente, que é o PhpStorm. Eu venho em “File”, “Settings”, e dentro de “Language as Frameworks”, eu venho em PHP e eu venho em “Debug”. E aqui, por padrão, isso já vem configurado corretamente, mas só para garantir você vai verificar que a porta é 9000, que é a padrão do XDebug.

- Se você estiver utilizando algum programa que utilize essa porta já, você pode mudar para qualquer valor aqui, mas aí você vai precisar atualizar essa configuração de remote port no seu “php.ini”. Eu vou deixar padrão aqui.

- A gente já está com isso aqui habilitado, como a gente mudou uma configuração no “php.ini”, eu vou derrubar o servidor web e subir de novo, ótimo, e agora a gente pode vir aqui, vou definir um breakpoint nesse meu arquivo, e eu vou clicar nesse botão, que significa que eu estou dizendo para o PhpStorm começar escutar por conexões de debug.

- Então eu cliquei, ele vai começar a ouvir as conexões, e agora, quando eu vir no meu navegador e garantir que isso está habilitado, botão direito e vou vir em “Opções” para fazer uma última configuração. Por padrão, não é o PhpStorm que vem habilitado, então a gente vai clicar aqui em PhpStorm para salvar, e agora sim, com o debug habilitado, eu vou atualizar a página.

- Quando eu atualizo, repara que está carregando aqui ainda, e o meu PhpStrom já está gritando, já está apitando. E aqui eu consegui fazer a depuração, conseguir parar a execução lá no meu navegador para fazer o debug aqui.

- Então aqui eu conseguiria navegar, entrar no método que eu quero entrar para garantir que o [XX-ininteligível-XX] está sendo executado corretamente, ver se esse SQL está sendo gerado corretamente. Então eu consigo fazer o debug normalmente de uma aplicação aqui exatamente igual se eu tivesse fazendo, utilizando o console, o PhpStorm direto, sem navegador.

- Então isso é fenomenal, isso é muito legal. A gente já consegue verificar aqui que o ID foi inserido, ou seja, o leilão foi inserido corretamente. Ele vai finalizar. Opa, entrou. Ele vai atualizar. E show de bola, finalizou. E aí ele finaliza a requisição aqui também.

- Então dessa forma a gente consegue configurar uma sessão remota de debug. De novo, como eu falei lá no início, é interessante você trabalhar com o PhpStorm por enquanto, pelo menos, para conseguir entender os conceitos, e vou deixar um exercício para configurar isso em algum outro editor, por exemplo, o Visual Studio Code. Já que ele não está na lista suportados oficialmente, eu vou dar uma pesquisada em tutoriais para você configurar o Visual Studio Code também.

- Mas eu recomendo fortemente que você utilize o PhpStorm devido a todas as outras facilidades que a gente já viu até aqui.

- Com isso, a gente encerra a sessão de debug remoto. Existe muita coisa que a gente pode fazer, mas a gente já tratou bastante coisa sobre a depuração no capítulo anterior. Então com isso você pode, por exemplo, buscar um pouco mais para configurar uma sessão de debug remoto com o docker, com uma máquina virtual, isso tudo é possível fazer. O PhpStorm inclusive te ajuda com isso, existem vários tutoriais, mas a ideia de debug remoto é basicamente essa: a gente tem um servidor, ou qualquer outro programa que faz uma conexão com o cliente de debug e, a partir disso, a depuração acontece.

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64548)
