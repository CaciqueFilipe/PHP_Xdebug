# Analisando a stack

- Agora eu quero gerar um erro, quero gerar, no caso, uma exceção, mas a gente vai funcionar da mesma forma com erro, na nossa aplicação. Eu quero gerar um caso onde a gente vai tentar receber um lance de um leilão já finalizado.

- Então vou criar um novo arquivo aqui chamado de _“Erro”_. É um arquivo PHP, eu não vou criar nenhuma estrutura HTML não, e vou criar um leilão. Esse leilão vai ser para um objeto muito legal, show de bola. Mas antes, obviamente, a gente precisa do nosso Autoloader. “Vendor”, “Autoload”. Agora sim. E aqui, esse nosso leilão, a gente já vai finalizar. Sem lance nenhum a gente vai finalizar, e agora a gente vai receber um lance.

- Então eu vou criar um novo lance, esse lance é de um usuário, o usuário Vinícius Dias, e esse lance tem um valor. Show de Bola. Deixa eu importar esse monte de classe. Com o PhpStorm, out e enter, e enter, ele já vai começar a importar. Out e enter, e enter, out e enter, e enter.

- Se você estiver utilizando qualquer outra Ide, basta adicionar os imports aqui e utilizar diretamente. Então a gente está recebendo um lance, que é um novo lance, do usuário Vinícius Dias, no valor de mil reais. Ok. Só que isso vai gerar um erro porque esse leilão já está finalizado.

- Então deixa eu subir um servidor aqui. **“Php –S”, “Local Host:8080”**. E agora eu vou abrir esse arquivo “erro.php”. E olha só que interessante que a gente tem aqui. Nós temos, além de toda a informação, erro fatal, e aqui a mensagem do erro fatal. Erro de qual exceção foi, e a mesma mensagem novamente, “Esse leilão já está finalizado”, então a gente já tem uma mensagem mais descritiva - e até redundante -, onde a gente tem tanto o erro fatal quanto a exceção, e aqui a gente tem a call stack, ou seja, a pilha de chamadas. Onde ele mostra por cada ponto em que o nosso código passou.

- Então aqui na função main, que seria o código principal que inicializou o script, que é no “erro.php”, depois a gente chamou um método da classe leilão chamado “recebe lance” no arquivo “erro.php” na linha 12. Então aqui na linha 12 a gente chamou o “recebe lance”, e esse “recebe lance” emitiu um erro. E aqui ele já mostra para a gente que foi na linha 30.

- Então além da linha do erro, ele mostra toda a pilha de execução até o erro acontecer. Com isso a gente consegue debugar, a gente consegue depurar, a gente consegue analisar exatamente todos os passos que aconteceram. Então aqui é uma chamada muito simples, mas em chamadas grandes, onde você tem um método, que chama outro método, que depois chama outro método até dar o erro, isso pode ser bastante útil para você analisar tudo que aconteceu.

- Então aqui a gente sabe que no código principal do “erro.php” chamou o “recebe lance” na linha 12. E na linha 12 o erro aconteceu, exatamente aqui. Então a gente pode analisar e vir aqui para entender o que aconteceu, e a gente vai achar. Esse leilão já está finalizado.

- Se eu tentar, por exemplo, dar um lance com o mesmo usuário mais de uma vez? Então eu não vou finalizar. Eu vou selecionar esse usuário aqui. No PhpStorm, “control+alt+v”, um usuário, e eu vou gerar um novo lance para ele. Então “control+d” para duplicar a linha, e eu vou gerar um novo lance. Isso vai gerar um outro erro para a gente poder analisar.

- Então quando eu atualizo, tem aqui, o usuário já deu o último lance. Então ele mostra que agora, na linha 14, esse erro está acontecendo. Então aqui, na linha 14, quando a gente dá o segundo lance.

- Então é interessante a gente pegar essas informações para analisar tudo o que aconteceu na aplicação até chegar naquele erro. Só que às vezes a gente precisa de mais informações. Além do passo a passo, a gente pode querer ver aqui de cara o valor de alguma variável, como, por exemplo, as variáveis que vieram do servidor através da requisição do “Post Get” etc. 


- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64537)
