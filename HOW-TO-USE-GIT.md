# How to use Git?

Aprenda os comandos básicos de versionamento da ferramenta Git.

## O que é Git?

É um sistema de controle de versões distribuído, usado principalmente no desenvolvimento de software, mas pode ser usado para registrar o histórico de edições de qualquer tipo de arquivo. O Git utiliza alguns comandos chaves para fazer o versionamento dos arquivos.

## Tópicos 

1. Como inicializar repositórios;
2. Como fazer o primeiro commit em um projeto;
3. Como realizar commit de mudanças;
4. Como compartilhar suas mudanças com outras pessoas da equipe;
5. Como desfazer alterações;
6. Como resolver conflitos de merge;
7. Como usar branches;
8. Como encontrar bugs (git diff, git log, git bisect, git blame);
9. Como escolher determinados commits.

## Antes de começarmos

Abra o seu projeto por um terminal, acessando a pasta raiz do projeto. Iremos rodar os comandos Git por meio desse terminal.

### Como inicializar repositórios?

Para iniciar um repositório, digite o terminal o comando:

`git init`

O retorno no terminal deve ser semelhante a:

```
Initialized empty Git repository in /.git/

Success!
```

### Como fazer o primeiro commit em um projeto?

Para criar um commit, primeiramente, você precisa ter mudanças nos seus arquivos. Modifique qualquer arquivo (pode ser até um .txt) e rode os seguintes comandos:

`git status` - para verificar as duas alterações. Os arquivos alterados estarão abaixo de `Untracked files`.

`git add .` ou `git add nome_do_arquivo` - para adicionar os arquivos alterados, chamamos isso de "colocar em stage".

`git commit -m 'mensagem'` - para criar o commit. O comando `-m` serve para adicionarmos uma mensagem ao commit, serve como uma etiqueta, para reconhecermos o commit mais facilmente.

### Como realizar commit de mudanças?

Para fazer um commit de mudanças, você pode fazer da mesma forma que o tutorial anterior:

`git add .`, `git add nome-do-arquivo` ou até `git add .txt` - para adicionar vários arquivos com a mesma extensão.

Seguido por `git commit -m 'mensagem'` para criar o commit.

### Como compartilhar suas mudanças com outras pessoas da equipe?

Para compartilhar seus commits em um repositório, você deve utilizar o comando `git push` para enviar as mudanças.

Porém, como estamos iniciando um repositório, precisamos definir uma origem, um local base para as nossas alterações serem enviadas. Para isso, use o comando `git remote add origin link-do-repositorio-no-github` para definir a origem e `git push -u origin master` para enviar as alterações.

### Como desfazer alterações?

Para desfazer alterações, você pode utilizar o comando `git reset` para retirar os seus arquivos de stage. O comando `reset` aceita os mesmos argumentos do comando `add`. Ou seja, você pode definir um arquivo especifico, todos os arquivos com uma extensão especifica ou todos os arquivos modificados.

### Como resolver conflitos de merge?

Quando muitos commits são enviados para um repositório, é normal existirem conflitos de código. Se o seu código tiver um trecho como este:

```
<html>
  <head>
  <<<<<<< HEAD
    <title>Hello World</title>
  =======
    <title>Olá Mundo</title>
  >>>>>>> master
  </head>
  <body>
    Lorem ipsum dolor sit amet consectetur ...
  </body>
</html>
```

Onde:

```
<<<<<<< HEAD
	Aqui está a sua alteração de código.
=======
	Aqui vai a alteração de outra pessoa que o Git tentou mesclar
>>>>>>> master
```

Significa que temos conflitos no código. Para isso, você pode alterar manualmente pelo código ou utilizar outros recursos, como o Visual Studio Code que demonstra as alterações de uma mais amigável. Após isso, commite suas resoluções:

```
git add nome-do-arquivo
git commit -m "Resolvendo conflitos"
git push
```

### Como usar branches

Para ajudar a organizar as nossas alterações, podemos criar uma **branch** (ou bifurcação/ramo) do código para que as mudanças fiquem anexadas em espelhos diferentes do repositório.

Para criar uma branch, use o comando `git branch nome-da-sua-branch`, após isso, você poderá anexar as duas mudanças somente na sua branch.

### Como encontrar bugs?

O Git possui alguns comandos que ajudam a encontrar bugs com mais facilidade, entre eles:

* `git diff HEAD` - para ver as mudanças feitas no ramo principal; 
* `git log` - para visualizar o histórico de alterações, como commits e andamento do projeto;
* `git bisect` - para fazer uma busca binária e encontrar o commit que originou um bug, você pode definir os commits pelo atributo `good` e `bad`;
* `git blame` - mostra quem modificou cada linha do arquivo, assim como so horários e informações gerais do commit.

### Como escolher determinados commits?

Para escolher um determinado commit, é utilizado o comando `git cherry-pick` que traz commits especificos para a branch desejada. Para utilizar, simplesmente use `git cherry-pick id-do-commit` para adicionar o commit a sua branch atual. Para pegar o id do commit, você pode utilizar o `git log` e copiar o id.
