# Git Assignment

**INDIVIDUAL**

**Entrega**: 23-Mar-21

Copie o arquivo em um repositorio que seja seu e coloque as respostas nas caixas abaixo
Abra uma issue nesse repositório aqui indicando o link para o arquivo no seu repo.

### Entenda o repositorio
Baixe o arquivo [handson.zip] (handson.zip) e descompacte-o
A pasta handson é um repositório git. Usando a linha de comando, altere o diretório para "handson/"


As caixas vazias
```

```
representam o conteúdo que você precisa preencher e postar em seu repositório privado

1. Descreva qual é a saída dos seguintes comandos
    -  `git branch` 
    -  `git checkout BRANCH_NAME` (USE THE NAME OF AN EXISTING BRANCH)
    -  `git log --decorate`

```
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git branch
  feature-foo
* master
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git checkout feature-foo
Switched to branch 'feature-foo'
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git log --decorate
commit a70a8e9d3c5390e367028faf033f2a9ef03d2e91 (HEAD -> feature-foo)
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:29:22 2018 -0700

    Adding header of method foo()

commit 309b0d73ff9c2163591c9e96e307fe61b4c8f58a
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:27:16 2018 -0700

    Adding class A skeleton

commit 9c1eeb8901b0926ce7fa13cc6ce0a1876fc4179b
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:26:44 2018 -0700

    Creating all files (all empty)

```

2. Tente usar `git log --graph --all`. O que acontece?
```
Aparece o histórico de edições

luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git log --graph --all
* commit f67f266cf420735187053f10d32e2c0f7cbc5a43
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Fri Aug 24 15:30:05 2018 -0700
| 
|     Adding class B skeleton
|    
| * commit a70a8e9d3c5390e367028faf033f2a9ef03d2e91
|/  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
|   Date:   Fri Aug 24 15:29:22 2018 -0700
|   
|       Adding header of method foo()
|  
* commit 309b0d73ff9c2163591c9e96e307fe61b4c8f58a
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Fri Aug 24 15:27:16 2018 -0700
| 
|     Adding class A skeleton
|  
* commit 9c1eeb8901b0926ce7fa13cc6ce0a1876fc4179b
  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
  Date:   Fri Aug 24 15:26:44 2018 -0700
  
      Creating all files (all empty)

```

3. Use `git diff BRANCH_NAME`  para ver as diferenças de um ramo e do ramo atual.
   Sumarize as diferenças do master e do outro ramo.

```
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git diff master
diff --git a/A.java b/A.java
index 3ea227e..674b8ce 100644
--- a/A.java
+++ b/A.java
@@ -1,4 +1,7 @@
 public class A {
-
+   
+   public void foo() {
+   
+   }
 
 }
diff --git a/B.java b/B.java
index ae64e6b..e69de29 100644
--- a/B.java
+++ b/B.java
@@ -1,4 +0,0 @@
-public class B {
-
-
-}

```

4. Escreva uma sequencia de comandos para mesclar o ramo não-master no `master`

```
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git config --global user.email "luizphilipe02@gmail.com"
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git config --global user.name "Luiz Philipe Alves"
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git merge master
Merge made by the 'recursive' strategy.
 B.java | 4 ++++
 1 file changed, 4 insertions(+)

```


5. Escreva um comando (ou sequência) para (i) criar um novo ramo chamado `math` (do` master`)
e (ii) mudar para este ramo

```
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git branch math
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git checkout math
Switched to branch 'math'
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git branch
  feature-foo
  master
* math

```
   
6. Edite B.java adicionando o código abaixo ao conteúdo do arquivo
```java
System.out.println("I know math, look:")
System.out.println(2+2)
```

7. Escreva o comando (ou sequencia) para realizar o commit de suas mudanças
```
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git commit .
[math 5d7feae] [SL-2021] Adicionando código de matemática
 1 file changed, 2 insertions(+)

```

8. Volte para o branch `master` e mude B.java adicionando o seguinte código-fonte (confirme sua mudança para` master`):
```java
System.out.println("Hello World")
```

9. Escreva uma sequência de comando para mesclar o branch `math` em` master` e descreva o que aconteceu
```
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git commit .
[master 14074ce] [SL-2021] HELLO WORLD!
 1 file changed, 1 insertion(+)
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git merge math
Mesclagem automática de B.java
CONFLITO (conteúdo): conflito de mesclagem em B.java
Automatic merge failed; fix conflicts and then commit the result.

```
   
10. Escreva um conjunto de comandos para abortar a mesclagem
```
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git merge --abort

```
   
11. Agora repita o item 9, mas prossiga com a mesclagem manual (Editando B.java). Todas as funções implementadas são necessárias. Explique o seu procedimento
```
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git merge math
Mesclagem automática de B.java
CONFLITO (conteúdo): conflito de mesclagem em B.java
Automatic merge failed; fix conflicts and then commit the result.
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git status
No ramo master
Você tem caminhos não mesclados.
  (fixar conflitos e executar "git commit")

Caminhos não mesclados:
  (usar "git add <arquivo>..." para marcar resolução)

	ambos modificados:   B.java

nenhuma modificação adicionada à submissão (utilize "git add" e/ou "git commit -a")
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git add B.java 
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git commit -m "[SL-2021] Resolução de conflito"
[master 3ad5002] [SL-2021] Resolução de conflito

```

12. Escreva um comando (ou conjunto de comandos) para prosseguir com a mesclagem e atualizar o branch `master`
```
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git remote add origin https://github.com/luizphilipe2/SL2021_handson.git
luiz@note-luiz:~/Documentos/MESTRADO/Software Livre/handson$ git push -u origin master
Username for 'https://github.com': luizphilipe2
Password for 'https://luizphilipe2@github.com': 
Counting objects: 21, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (18/18), done.
Writing objects: 100% (21/21), 2.03 KiB | 0 bytes/s, done.
Total 21 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), done.
To https://github.com/luizphilipe2/SL2021_handson.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.


```



