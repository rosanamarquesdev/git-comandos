# git-comandos

Arquivo de pesquisa:
```bash
https://www.freecodecamp.org/portuguese/news/10-comandos-do-git-que-todo-desenvolvedor-deveria-conhecer/
```

- PUSH
- Apos fazer o commit. Enviar as alteracoes (atualizar) para o servidor remoto

```bash
    git push <repositorio-remoto> <branch>
```

Entretanto, se a sua branch foi recém-criada, também é preciso fazer o upload da branch com o seguinte comando:

```bash
    git push --set-upstream <repositório-remoto> <nome-da-branch>
```

ou

```bash
    git push -u origin <nome-da-branch>
```

**GIT MERGE**
- Mude (git checkout) para branch que vai receber as modificacoes que foram feitas em outra branch
- Antes de git merge (na branch que vai receber as modificoes feitas em outra branch) dê o comando:

```bash
    git pull
```
depois de o merge(o nome_da_branc é a branch que vai "doar as novas modificacoes"):

```bash
    git merge nome_da_branch
```



**Criar uma nova branch:**



## Erro:

```bash
* branch            main       -> FETCH_HEAD
Already up to date.
```

**Explicacao:**
Seu repositorio local esta igual o repositorio remoto (nessa branch).

**FAZER O COMANDO:**

```bash
    fazer alguma alteracao no arquivo ou entao mudar para a branch que tem as modificacoes
```


```bash
fatal: No configured push destination.
Either specify the URL from the command-line or configure a remote repository using
    git remote add <name> <url>
and then push using the remote name
    git push <name>
```
**Explicacao:**
Sua maquina local nao esta conectada a nenhum repositorio do github.

**FAZER O COMANDO:**

```bash
    git remote add origin url_do_repositorio
```

## Erro:

```bash
fatal: The current branch nome_da_branch has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin nome_da_branch
```

**Explicacao:**
Voce nao definiu para qual branch vai enviar.

**FAZER O COMANDO:**

```bash
    git push --set-upstream origin nome_da_branch
```

- Acontece quando você cria uma branch nova e tenta da o push pela primeira vez daquela branch

## Erro:

```bash
! [rejected] master -> master (non-fast-forward) error: failed to push some refs to 'https://github.com/USERNAME/REPOSITORY.git' hint: Updates were rejected because the tip of your current branch is behind hint: its remote counterpart. Integrate the remote changes (e.g. hint: 'git pull ...') before pushing again. hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

**Explicacao:**
O estado da sua branch não é o mesmo da que está no github, você precisa sincronizar com git pull e depois rodar git push novamente.

**Pode causar esse problema** 
- Criar o repositorio no github com o README (pois perde a sincronizacao inicial por nao esta mais vazio)

**FAZER OS COMANDO:**

```bash
    git pull origin nome_da_branch
```
depois fazer:

```bash
    git push origin nome_da_branch
```

## Erro:

```bash
    fatal: refusing to merge unrelated histories
```

**Explicacao:**
O estado da sua branch não é o mesmo da que está no github, você precisa sincronizar com git pull e depois rodar git push novamente.

```bash
    git pull origin main --allow-unrelated-histories
```

**Explicacao:**
- Acontece quando você tenta fazer o git pull de um repositório remoto, mas o seu repositório local possuí um histórico de commits, branches, etc, diferente do que está no repositório remoto.

- Para permitir que o Git faça o merge de dois projetos com históricos diferentes, é só passar o parâmetro --allow-unrelated-histories quando for fazer o pull, assim:

```bash
    git pull origin nome_da_branch --allow-unrelated-histories
```

Depois para subir normalmente para o repositorio:

```bash
    git push origin nome_da_branch
```

