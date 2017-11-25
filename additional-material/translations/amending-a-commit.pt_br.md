## Corrigindo um Commit

E se você der Commit numa mudança para o seu repositório remoto e só perceba depois um erro de digitação na mensagem de Commit, ou que se esqueceu de adicionar uma linha no seu Commit mais recente?
Como você corrigiria isso? É isso que esse tutorial ensina.

### Modificando a mensagem de um Commit recente depois de dar Push para o Github
Para fazer isso sem abrir um arquivo:
* Digite o comando ```git commit --amend -m "Sua nova mensagem de Commit"```
* Rode ```git push origin <nome-do-branch>``` para dar Commit nas mudanças no repositório.

Nota: Se você digitar apenas ```git commit --amend```, seu editor de texto abriria pedindo para você editar a mensagem de Commit.
Adicionar o ``-m`` previne isso.

### Modificar apenas um Commit

Agora, e se esquecermos de fazer uma mudança pequena em um arquivo, como modificar uma única palavra, mas já demos Push para nosso repositório remoto?

Para ilustrar, aqui está o registro dos meus Commits:
```
g56123f criar arquivo botfile
a2235d atualizar contributor.md
a5da0d modificar botfile
```
Vamos dizer que eu esqueci de adicionar uma única palavra ao arquivo bot file.

Há duas maneiras de se fazer isso. A primeira é fazer um Commit totalmente novo que contém a mudança, como:
```
g56123f create file botfile
a2235d updated contributor.md
a5da0d modified botfile
b0ca8f added single word to botfile
```
A segunda maneira é corrigir o commit a5da0d adicionando essa palavra nova e dar Push para o GitHub como um único Commit.
A segunda parece melhor, já que essa é uma alteração muito pequena.

Para conseguir isso, faríamos o seguinte:
* Modifique o arquivo. Nesse caso, eu vou modificar o botfile para incluir a palavra que foi omitida anteriormente.
* Depois, adicione o arquivo à área de preparação (*staging area*) com ```git add <nome-do-arquivo>```

 Normalmente, depois de adicionar arquivos à área de preparação, a próxima coisa a se fazer seria digitar `git commit -m "mensagem do commit"`, certo?
 Mas já que o que queremos aqui é corrigir o último commit, no lugar rodaríamos o seguinte:

* ```git commit --ammend```
Isso iria então abrir o editor de texto para que você edite a mensagem. Você pode deixar a mensagem como era antes ou mudá-la.
* Saia do editor
* Dê Push nas mudanças com ```git push origin <nome-do-branch>```

Desse modo, ambas as modificações estarão em um mesmo Commit.
