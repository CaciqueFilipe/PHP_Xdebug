# Consolidando o seu conhecimento

## _Chegou a hora de você pôr em prática o que foi visto na aula. Para isso, execute os passos listados abaixo._

- 1) Execute o comando vendor/bin/phpunit --filter testBuscaLeiloesNaoFinalizados para executar o teste. Veja que ele falha.

- 2) No método testBuscaLeiloesNaoFinalizados, da classe de testes LeilaoDaoTest, adicione um var_dump para analisar o valor de $leiloes. Execute o comando do passo 1 novamente e analise a saída.

- 3) Na classe Leilao, do namespace Dao, corrija o método recuperarNaoFinalizados, trocando true por false. Execute novamente o teste (do passo 1) e veja que agora ele passa. Remova o var_dump adicionado no passo 2.

- 4) Na raiz do projeto, crie um arquivo chamado var_dump.php, com o seguinte conteúdo:

```
<?php

require __DIR__ . '/vendor/autoload.php';

$leilao = new \Alura\Leilao\Model\Leilao('Fiat 147 0Km');

var_dump($leilao);

echo "Teste";COPIAR CÓDIGO
```

- 5) Utilizando o PHPStorm, clique com o botão direito do mouse sobre o arquivo, e vá em Abrir no navegador.

> Se você não estiver utilizando o PHPStorm, inicie um servidor web pela linha do comando (php -S localhost:8080) e acesse http://localhost:8080/var_dump.php no navegador.

- 6) Siga as instruções do seguinte link, para instalar o Xdebug: https://xdebug.org/docs/install.

- 7) Inicialize outro servidor web e acesse o arquivo var_dump.php pelo navegador. Note que a exibição agora está melhorada.

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/65303)
