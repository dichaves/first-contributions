## Revertendo um Commit

Para reverter um Commit, basta criar um Commit novo que desfaz todas as mudanças feitas no anterior. É como dar um ```CTRL + Z ``` no git.

A reversão se torna mais fácil no git, porque todo Commit que você dá Push para seu repositório remoto tem uma chave alfanumérica única, conhecida como SHA (Secure Hash Algorithm), ligada a ele.
Isso quer dizer que você pode reverter qualquer Commit, contanto que tenha seu SHA.
Porém, você precisa ter o cuidado de reverter ordenadamente, de forma a não bangunçar seu repositório.


Para selecionar o SHA do Commit que queremos desfazer, um registro de todos os Commits feitos até agora viria a calhar.
Para conseguir esse registro, usaríamos o comando: ```git log --oneline ```.
Rodar apenas ```git log``` também nos daria os SHAs (em forma longa), mas o Flag ```--oneline ``` diz ao git que os queremos exibidos de maneira concisa (em uma linha) para facilitar a leitura.

Os primeiros 7 caracteres mostrados quando se roda esse comando formam uma abreviação do SHA. Por exemplo, aqui está o que aparece quando eu rodo  ```git log --oneline ``` nesse repositório:
```
389004d added spacing in title
c1b9fc1 Merge branch 'master' into tutorials
77eaafd added tutorial for reverting a commit
```

Isso mostra que, com ```git log --oneline```, é possível obter uma lista de todos os Commits feitos no repositório, acompanhados dos 7 primeiros caracteres de seus respectivos SHAs.

Agora, vamos assumir que eu quero desfazer meu commit de "added spacing in title". Aqui estão os passos que eu tomaria:

* Copiar o SHA do Commit, que nesse caso é ```389004d```
* E então rodar o comando ```git revert 389004d```

Isso abriria meu editor de texto e me induziria a editar a mensagem de Commit.
Você pode decidir deixar a mensagem padrão do git, que começa com a palavra `Revert`, ou então poderia customizá-la ao seu gosto.

* Então, eu salvo e fecho o editor de texto.
* Volto à linha de comando.
* Rodo ```git push origin <nome-do-branch>``` para dar Push nas mudanças revertidas para o Github.

E é isso, a mudança seria desfeita. Nesse caso, meu repositório voltaria a ser como era em ```c1b9fc1```.
