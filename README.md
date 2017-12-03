#  Git comandos


**git config --global user.name <informar_username>**

**git config --global user.email informar_email**

**git init**
-    Transforma o seu diretorio em um repositorio gerenciavel pelo GIT. 

**git add nome_arquivo**
-  Comando utilizado para informarmos ao Git que desejamos rastrear determinado arquivo, incluindo-o no controle de versão.
-  Em nome_arquivo pode ser utilizado:
    -  **o nome do arquivo** (git add index.html)
    -  **um ponto (.) ou um asterisco (*)** , para adicionar todos os arquivos do diretório (git add . / git add *)
    -  **path ou caminho do arquivo** (git add /src/index.html)
    -  **-i**, para adicionar utilizando o modo interativo (git add -i)

**git reset HEAD doc.txt**
- remover arquivo do monitoramento do git 

**git commit -m "Descricao para a mensagem"**
- Comitando localmento as aterações e passando uma mensagem
- -a : inclui imediatamente no commit todos os arquivos modificados ou removidos, mas não inclui arquivos novos!

**git status**
- mostra o status atual do repositorio(se ocorreu alguma alteração e quais)

**git remote**
-  verifica se existem repositorios remotos adicionados

**git remote add nome_repositorio url_repositorio**
- utilizado para adicionar um repositorio remoto (git remote add origin https://github.com/daniel-tavares/git-comandos.git)

**git clone url_repositorio**
- Realizar o download do repositorio remoto para a maquina local (git clone https://github.com/daniel-tavares/git-comandos.git)

**git push nome_repositorio_remoto nome_da_branch**
- para enviar os dados do repositorio local para o repositorio remoto (git push origin master)
- **-u :** utilizado para parear uma branch local e uma branch remota, evitando falha ao realizar o git pull sem parametros. (git push -u origin desenvolvimento)

**git pull nome_repositorio_remoto nome_da_branch**
- para sincronizar o repositorio local com o conteudo do repositorio remoto. (git pull origin master)

**git branch**
- exibe as branchs locais existentes
- **-r :** mostra somente as branchs remotas
- **-a:** lista as branchs locais e remotas
-   
**git brach nome_da_branch**
-  utilizado para criar uma nova branch (git branch desenvolvimento)
- **-D:** utilizado para deletar uma branch local (git branch -d desenvolvimento)
- Para deletar uma branch remota temos as opções:
    - git push -d origin desenvolvimento
    - git push origin :desenvolvimento

**git checkout nome_da_brach**
- mudar para uma determinada branch (git checkout desenvolvimento)
- **-t nome_da_branch_local nome_da_branch_remota:** para criar uma branch local, passar para a nova branch criada e sincronizar com a branch remota (git checkout -t desenvolvimento origin/desenvolvimento)
- **-b:** cria a branch(git branch) e migra para a nova branch(git checkout) apenas utilizando o checkout (git checkout -b desenvolvimento)

**git fetch nome_repositorio_remoto**
- verificar se existe alguma alteração no repositório remoto, dentre elas a criação de novas branchs (git fetch origin)

**git rebase master desenvolvimento**
- utilizado como boa pratica para sincronizar commite a commite dois repositório, neste caso, a branch desenvolvimento deve tomar como base a branch master
- **git rebase master** se estiver executando o comando de dentro da branch  desenvolvimento
- o git reabase faz com que a branch em que se está tenha um novo HEAD, "copiado" de outra branch
- 
**git rebase --continue**
-  Utilizado para dar continuidade ao rebase. Após a resolução de um conflito
-  
-  **--abort**  abortar o rebase
-  **--skip** pular o commit que causa o conflito

**git log**
- mostra o histórico de commits
-
**git whatchanged**
- mostra o historico de commits de forma mais detalhado
- - p : mostra o que foi alterado (git whatchenged -p)

**git tag:** 
- verificar quais são as versões definitivas ou releases. (tag1.1,tagv1.2)

**git diff tav1.1 tag1.2:** 
- Mostra o que tem de diferente entre as tags citadas (o que entrou, o que saiu)

**git rm --cached -rf nome_do_arquivo_ou_diretório**  
- remover arquivos remotos

**git blame css/index.css:** 
- mostra as alterações linha por linha no arquivo, 
- informar qual o commit essa linha foi inserida,   
- informa qual nome do arquivo quando a linha foi alterada 
- Mostra quem alterou o arquivo

**git  ls-files**
- mostra os arquivos que estão sendo controlados pelo git

## RESOLVER CONFLITO (Quando o mesmo arquivo é alterado nas mesmas linhas)
- **Passo1:** git pull origin desenvolvimento
- **Passo2:** ajustar os arquivos conflitantes através da IDE ou editor de texto (HEAD é representa o código local)
- **Passo3:** git add .
- **Passo4:** git commit -m 'mensagem'
- **Passo5:** git push origin desenvolvimento

**git mergetool --tool-help**
- Exibe uma lista de interfaces graficas para tratar conflitos

**git mergetool -t emerge**
- utilizado para carregar uma interface grafica para resolver conflito
- 





