# Consolidando o seu conhecimento


_Chegou a hora de você pôr em prática o que foi visto na aula. Para isso, execute os passos listados abaixo._

- 1) Abra o seu arquivo **php.ini** em qualquer editor de texto. Garanta que a opção display_errors esteja habilitada.

- 2) No arquivo _var_dump.php_, altere a linha com o var_dump para var_dump($leilao1);.

- 3) Compare as saídas nos servidores web com e sem o Xdebug instalado.

- 4) Desabilite a opção **display_errors**, reinicie o servidor web e note que o erro não é mais exibido.

- 5) No final do arquivo php.ini, adicione a seguinte configuração:
```
xdebug.force_display_errors=1
```

- 6) Reinicie o servidor web e note que o erro volta a ser exibido.

- 7) No php.ini, altere o **error_reporting=E_WARNING**. Repare que o erro não é mais exibido.

- 8) No final do arquivo php.ini, adicione a seguinte configuração:
```
xdebug.force_error_reporting=E_ALL
```

- 9) Reinicie o servidor web e note que o erro volta a ser exibido.

- 10) No final do arquivo php.ini, adicione a seguinte configuração:
```
xdebug.halt_level=E_NOTICE
```

- 11) Reinicie o servidor e note que a execução do script para na linha com erro.

- 12) No final do arquivo php.ini, adicione a seguinte configuração:
```
xdebug.scream=1
xdebug.cli_color=2
xdebug.var_display_max_depth=1
xdebug.var_display_max_data=5
```

- 13) Execute o comando php var_dump.php e repare que na linha de comando, a saída está colorida, com as informações sendo exibidas conforme as nossas configurações.


- Fonte: [alura](https://cursos.alura.com.br/course/php-xdebug-profiling/task/65305)

