# Consolidando o seu conhecimento

Chegou a hora de você pôr em prática o que foi visto na aula. Para isso, execute os passos listados abaixo.

1. Crie um arquivo chamado atualizar-leilao.php, com o seguinte conteúdo:

```
<?php

use Alura\Leilao\Dao\Leilao as LeilaoDao;
use Alura\Leilao\Model\Leilao;

require_once __DIR__ . '/vendor/autoload.php';

$pdo = new \PDO('sqlite::memory:');
$pdo->exec('create table leiloes (
    id INTEGER primary key,
    descricao TEXT,
    finalizado BOOL,
    dataInicio TEXT
);');

$leilao = new Leilao('Brasília Amarela');
$leilaoDao = new LeilaoDao($pdo);
$leilao = $leilaoDao->salva($leilao);

$leilao->finaliza();
$leilaoDao->atualiza($leilao);
```

2. No projeto, crie uma pasta chamada profiling.

3. No final do arquivo php.ini, adicione a seguinte configuração:

```
xdebug.profiler_enable=1  
xdebug.profiler_output_dir="/caminho/absoluto/para/pasta/profiling/recem/criada"
```

4. Pare todos os servidores web e execute o comando *php atualizar-leilao.php*, para executar este código e gerar o profiling.

5. Baixe o projeto do **WebGrind** nesta URL: [https://github.com/jokkedk/webgrind](https://github.com/jokkedk/webgrind).

6. Na pasta baixada, digite o comando *composer serve*.

7. Acesse *http://localhost:8080* para ver a interface do **WebGrind**.

8. Na caixa de seleção no canto superior direito, selecione o arquivo de profiling referente à execução do *atualizar-leilao.php*.

9. Defina a opção show como 100% e selecione microseconds na última caixa de seleção. Em seguida, clique em **update**.

10. Analise as informações disponíveis na página.


- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/65311)

