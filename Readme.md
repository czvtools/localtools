# localtools

Playground of tools to install and configure localy.


### How it all started

```bash
read GIT_USER
git init
mkdir -p .ssh
ssh-keygen -b 4096 -N '' -C "${GIT_USER}" $PWD/.ssh/id_rsa
cat $PWD/.ssh/id_rsa.pub
echo "Upload the key to GitHub ... press Enter to continue"
read
git config core.sshCommand "ssh -o IdentitiesOnly=yes -i ${PWD}/.ssh/id_rsa -F /dev/null"
git config --local user.name "${GIT_USER}"
git config --local user.email "${GIT_USER}@gmail.com"
git remote add origin git@github.com:${GIT_USER}/${PWD##*/}.git
git branch -M main
echo '.*/' > .gitignore
git add .gitignore
git commit -m "start with ignore"
git push -u origin main
```
