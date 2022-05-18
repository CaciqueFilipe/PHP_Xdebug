# Analisando os parâmetros

- Só que seria interessante também a gente saber qual foi o parâmetro passado aqui para “recebe lance”. E a gente tem uma configuração aqui do Xdebug que se chama collect params, onde o padrão é 0, que é o que a gente está vendo, onde a gente simplesmente não vê nenhuma informação de parâmetros.
```
xdebug.collect_params=0
```

- Se eu mudar isso aqui para um, vamos ver o que acontece. Vou executar a mesma chamada, e olha só, ele já mostra que está enviando um objeto aqui, um objeto do tipo um “lance”. Ok, mas isso eu já sei. No nosso caso aqui, isso já não ajuda muito. Às vezes saber que aqui foi passado uma string em vez de um inteiro, por exemplo, já ajudaria. Mas no nosso caso, não. Eu quero ver os valores.
```
xdebug.collect_params=1
```

- Se eu mudar para de 1 para 2, vou cancelar o servidor e subir de novo, e eu exibir, atualizar, aparentemente nada mudou, mas se eu passar o mouse aqui, repara que ele já mostra para gente, numa tool tip, num title, o conteúdo desse parâmetro “lance”, e a gente consegue ver lá que a gente está passando um usuário.
```
xdebug.collect_params=2
```

- Mas eu não quero ter que passar o mouse. Se eu quiser ver isso diretamente na tela, eu posso mudar aqui para 3. Vou parar, subir de novo, e olha só, quando eu atualizo, eu tenho as informações aqui, direto. Então eu estou vendo que eu estou passando um usuário, aqui nesse lance ele tem usuário, e eu estou vendo qual o valor. Eu estou passando aqui o valor 1500.
```
xdebug.collect_params=3
```

> Opa, então eu sei que o erro aconteceu na segunda chamada, sem precisar analisar a linha do erro. Eu sei que está dando erro na chamada que está passando o valor de 1500 reais.

- Então existem essas diferenças na forma de utilizar o collect params, e aqui a gente consegue analisar todas essas diferenças. O padrão é não exibir nada. Com o valor definido comum, a gente vê só o tipo do dado. Pegando dois, a gente vê o tipo do dado, mas tem acesso ao conteúdo dele passando o mouse em cima. Como um parâmetro com essa configuração passado como 3, a gente já vê todo o conteúdo. E, em 4, a gente vê inclusive o nome do parâmetro da variável que foi passada.
```
xdebug.collect_params=4
```
> Então, se eu mudar aqui para 4 e interromper aqui e subir de novo no servidor, repara que quando eu atualizar, ele mostra aqui, que esse valor, essa classe, está indo para o meu parâmetro “lance”.

- Então a gente já consegue ter informações ainda mais precisas direto aqui na nossa call stack. Isso é um problema em alguns casos. Primeiro problema, a gente vê que começa a ser bombardeado com muita informação. Às vezes a gente não quer saber disso tudo de cara. Eu, Vinícius, opção padrão minha, eu gosto de deixar isso aqui como 2, porque dessa forma eu tenho o melhor dos dois mundos. Eu tenho uma exibição mais simples, mas caso eu precise do conteúdo completo, eu posso passar o mouse.

- Então a primeira desvantagem é que ele exibe muita informação para a gente, e a segunda é que isso custa um pouquinho, ele gasta um pouco de performance. O Xdebug precisa de algum processamento para conseguir realizar essa coleta dos dados.

- Então, o número de memória consumida e o tempo que vai levar até ele gerar essa tela, pode demorar um pouquinho, pode aumentar um pouquinho mais esse tempo. Mas, como a gente está vendo aqui, coisas de microssegundos, então é bem rápido. Em nosso caso, numa aplicação assim, não vai influenciar em nada. Em uma aplicação onde você tem um milhão de variáveis sendo definidas, sendo passados, o que já é errado, ou se você tem um processo que leva 5 minutos para executar, isso pode acabar agravando a situação. Mas em casos normais, esse não é um problema tão grande.

- Agora a gente já analisar o parâmetro que foi passado para a função que gerou o erro, para o método que gerou o erro. Mas e se eu tiver, como eu falei no vídeo anterior, e se eu estiver dependendo de alguma variável global? E se eu estiver dependendo de dados da requisição? Como eu exibo isso, como eu posso falar: “Xdebug, eu quero mostrar, além da minha call stack, eu quero mostrar as de variáveis disponíveis quando deu o erro”. 

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/64538)
