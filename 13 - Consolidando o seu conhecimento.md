# Consolidando o seu conhecimento

_Chegou a hora de você pôr em prática o que foi visto na aula. Para isso, execute os passos listados abaixo._

- 1) Crie um arquivo chamado erro.php, com o seguinte conteúdo:

```
<?php

use Alura\Leilao\Model\Lance;
use Alura\Leilao\Model\Leilao;
use Alura\Leilao\Model\Usuario;

require_once __DIR__ . '/vendor/autoload.php';

ini_set('xdebug.dump.GET', '*');
$leilao = new Leilao('Um objeto muito legal');

$umUsuario = new Usuario('Vinicius Dias');

$leilao->recebeLance(new Lance($umUsuario, 1000));
$leilao->recebeLance(new Lance($umUsuario, 1500));
```

- 2) Acesse esse arquivo pelo navegador e analise a Call stack.

- 3) No final do arquivo php.ini, adicione a seguinte configuração:

```
xdebug.collect_params=1
```

- 4) Reinicie o servidor e note a diferrença na stack. Modifique este valor com números entre 0 e 4 (lembre-se de reiniciar o servidor web a cada mudança) e compare o resultado.

- 5) No final do arquivo **php.ini**, adicione a seguinte configuração:

```
xdebug.dump_globals=On
xdebug.dump.SERVER=*
xdebug.show_local_vars=On
```

- 6) Reinicie o servidor e analise as informações extras sendo exibidas.

- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/65308)
