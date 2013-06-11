============================
Receitas básicas com ``git``
============================

Criar e publicar um repositório
-------------------------------

Dentro de um diretório que será a raiz do seu repositório::

    touch README.rst
    git init
    git add README.rst
    git commit -m "primeiro commit"

Se o repositório já tem ao menos um *commit*, ele pode ser publicado no **GitHub** desta forma::

    git remote add origin https://github.com/«nome_conta»/«nome_repo».git
    git push -u origin master

Lista de arquivos a ignorar
---------------------------

É possível criar uma lista de nomes de arquivos ou padrões de nomes a serem ignorados por comandos como ``git status`` etc. Em geral um repositório git contém um arquivo ``.gitignore`` em seu diretório raiz, que é versionado junto com o resto do projeto. Listas ``.gitignore`` podem também existir em sub-diretórios do repositório.

Para usar uma lista de exclusão não versionada, edite o arquivo ``.git/info/exclude`` ou indique outra lista na configurção ``core.excludesfile``.

Referência: https://www.kernel.org/pub/software/scm/git/docs/gitignore.html


Configurações básicas
---------------------

Configurar nome e e-mail para registro de commits::

    git config --global user.name "Fulano de Tal"
    git config --global user.email fulano@tal.com

Configurar editor para mensagens de commit e edição interativa das configurações::

    git config --global core.editor «editor»

Conferir configurações ativas::

    git config -l

Editar configurações interativamente::

    git config -e

A opção ``--global`` cria configurações em ``~/.gitconfig``. Omita ``--global`` quando quiser alterar a configuração local em um repositório específico.


Criar um atalho para um comando longo
-------------------------------------

Exibir log com uma linha por *commit*, incluindo a árvore de branches::

    git log --oneline --graph

Para criar um atalho chamado ``glo`` abreviando o comando acima::

    git config --global alias.glo 'log --oneline --graph'



