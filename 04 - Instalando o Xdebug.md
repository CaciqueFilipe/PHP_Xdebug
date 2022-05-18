# Instalando o Xdebug

- Essa ferramenta é uma das ferramentas mais poderosas que eu conheço para o PHP, e ela tem algumas funcionalidades. Uma delas é auxiliar na depuração do código. Ela faz algumas outras coisas que a gente vai ver durante esse treinamento também, obviamente não tudo, mas algumas outras coisas, mas a gente vai focar, nesse momento, na parte de depuração de código.

- A gente poderia vir aqui em [download](https://xdebug.org/docs/install) e baixar alguma versão do Xdebug aqui, e repara que tem várias versões. Mas é difícil às vezes a gente saber qual versão é compatível com a versão do PHP que a gente está utilizando, são muitos downloads aqui quando a gente trabalha com Windows. No Linux a gente teria que talvez baixar o código-fonte e compilar. Nem sempre isso é tão simples.

- Então aqui existe uma página de instruções de instalação. Se você está utilizando um Linux ou Mac e você tem você tem o picle instalado, essa ferramenta, que normalmente vem junto com o PHP quando você instala através da linha de comando, através de um repositório, você pode simplesmente rodar esse comando e pronto, o Xdebug já está instalado.

- No nosso caso, como a gente está utilizando o Windows, a gente tem algumas opções. Uma é, de novo, vir aqui na página de download e baixar a DLL para versão do PHP que a gente está utilizando, ou a gente pode analisar essas instruções aqui, que é bem interessante.

- Vamos lá. Aqui ela já diz que essa página ajuda a encontrar qual arquivo baixar, e como configurar o PHP Xdebug. Ele diz que para ele ajudar a gente, ele precisa saber algumas informações da nossa instalação do PHP. Então a gente pode pegar a saída desse comando, “php-i”, e colar aqui. Ou a saída do “php.info”, essa função aqui que exibe uma página HTML bem legal, com todas as informações do PHP.

- Então vamos utilizar essa segunda abordagem. A gente vai utilizar a função “php.info”. Então eu vou utilizar esse mesmo arquivo var_dump aqui e só vou chamar a função “php.info”. “php.info”. Quando eu acessar aqui eu vou subir um servidor daquele PHP embutido.

- Então, “php-s localhost:8080”. OK. Assim a gente sobe um servidor web, eu vou acessar essa URL aqui, “/var_dump.php”. OK. Agora a gente tem, olha só que legal, todas as informações do nosso PHP com as informações de compilação, enfim, bastante coisa.

- Eu posso simplesmente copiar isso aqui, então eu vou dar “control+a”, “control+c” para copiar tudo, e vou colar aqui. Ele vai analisar o que tem nesse botão, e olha só: ele já verificou que a gente não tem o Xdebug instalado, está utilizando o servidor HTTP do próprio PHP, enfim. Ele mostra algumas informações e já dá para a gente qual arquivo baixar.

- No nosso caso, na versão do PHP que eu tenho, que é a versão 7.3, essa é a versão mais nova disponível. Se você estiver assistindo esse treinamento em outro momento em que há uma versão mais nova do Xdebug, eu vou deixar aqui o link para essa versão específica, que é 2.7.3 do Xdebug.

- Então beleza. Vou baixar esse arquivo, e aqui ele já diz para a gente para manter, mover essa DLL para a pasta “Ext”. Então vamos lá. Vou recortar, acessar a minha pasta do PHP, então deixa eu achar a pasta do PHP, e mover para “Ext”. Está lá. Vamos ver o próximo passo.

- Editar o arquivo “php.ini”, e olha que ele até mostra o caminho do meu “php.ini”, e adicionar essa linha aqui. Então deixa eu copiar essa linha, e vamos acessar o nosso arquivo “php.ini”.

- Eu vou abrir o “Notepad ++”, o meu “php.ini” já está aqui. Então “[XX-ininteligível-XX] extension”, não tem nenhuma, então eu vou colocar, lá no final do arquivo, essa linha aqui. Eu posso até remover esses espaços, eu gosto, eu sou meio chatinho com isso. Removi os espaços.

- Ok. Vamos ver o que falta. Reinicie o servidor web. Vamos reiniciar então. “Control+c” para parar o servidor, vou subir de novo e, opa, apareceu um errinho aqui, vamos ver o que aconteceu. “Não foi possível encontrar o módulo especificado”. Ele não encontrou o arquivo. Vamos fazer de outra forma, então.

- Eu vou remover esse “Ext” aqui e ver se agora ele encontra. Perfeito. O que aconteceu? O meu “php.ini”, deixa eu mostrar para vocês, já foi configurado para buscar as extensões dentro da pasta “Ext”, certo, com essa linha aqui, “extension id = ext”.

- Então, quando eu estava adicionando o “Ext” aqui, ele estava buscando uma pasta “Ext” dentro de “Ext”. No meu caso, não precisa disso.

- Mas agora a gente já tem essa configuração feita, o servidor web subiu de novo, então vamos executar mais uma vez o “php.info”, atualizei, agora vou pesquisar por Xdebug. E olha só, ele já mostra para a gente que o Xdebug está instalado.

- Então a gente começou, deu o primeiro passo para utilizar essa ferramenta maravilhosa que é o Xdebug. A instalação no Windows é um pouco mais chatinha, mas o Xdebug faz ser o mais fácil possível para a gente. Mas como eu falei, se você utiliza Linux ou Mac, apenas executar “picle install Xdebug” já resolve o seu problema, você já vai ter o Xdebug configurado.

- Caso você tenha compilado o PHP na mão, o que eu recomendo para estudos, que é bem interessante, é um aprendizado legal, caso você tenha compilado o PHP na mão, você vai precisar baixar o código-fonte do Xdebug também e compilar ele, mas não é um processo difícil, garanto que é bem tranquilo. Se você conseguiu compilar o PHP, você vai conseguir compilar o Xdebug sem problema nenhum.
