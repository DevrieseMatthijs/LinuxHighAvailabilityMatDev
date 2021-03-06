# Cheat sheet

Use this file to write down the most important commands you encounter, so you can look them up quickly. Put some clear structure in this document, or split it up if it becomes too large. [Use Markdown correctly](https://help.github.com/articles/getting-started-with-writing-and-formatting-on-github/). For inspiration and a motivation for why you should keep this type of cheat sheets, take a look at <https://github.com/bertvv/cheat-sheets/>.

## Vim survival guide

- When starting up Vim, you're in *normal mode*.
- To enter text, first go to *insert mode*.

| Taak                       | Commando |
| :---                       | :---     |
| Normal mode -> insert mode | `i`      |
| Insert mode -> normal mode | `<Esc>`  |
| Opslaan                    | `:w`     |
| Opslaan en afsluiten       | `:wq`    |
| Afsluiten zonder opslaan   | `:q!`    |

## Git commands

- SSH Key
	- `ssh-keygen`
	- ssh map en id_rsa.pub kopieren
	- pasten in settings github ssh

- Clone repository with ssh
	- `git clone git@github.com:example/example.git`

- Pull
```
git checkout master 
git pull upstream master
git checkout nick
git rebase master
```
- Push
```
git add .
git commit -m "what has changed?"
git push
```



