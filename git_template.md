## GIT
#### Initial configuration
```sh
git config --global user.name "name"
git config --local user.email "email"
git config --system core.editor "editor"
```
#### Remove user settings/logout cli
```sh
git config --global --unset user.name
git config --global --unset user.email
or 
git config --global --unset-all
```
####  Adding ssh keys 
```sh
1. ssh-keygen -t rsa 
2. ssh-add "KEY"
    ssh-agent -s
    eval $(ssh-agent -s)
    ssh-add "PATH TO FILE"
3. add public key to git repository
```
#### Creating git repository 
```sh

(existing project)

git clone git@xyz.org:user_name/repo_name.git
cd repo_name
echo "# My project's README" >> README.md
git add README.md
git commit -m "initial commit"
git push -u origin master

(from scratch)

git init
git add README.md
git commit -m "initial commit"
git remote add origin git@github.com:thefr33radical/repo_name.git
git push -u origin master
```

#### Delete remote folder
```sh
git checkout master
git rm -r folder-name
git commit -m "Remove duplicated directory"
git push origin master
```

#### Grive for Linux
```sh
sudo add-apt-repository ppa:nilarimogard/webupd8
sudo apt-get update
sudo apt-get install grive
sudo apt-get install cmake build-essential libgcrypt11-dev libjson0-dev libcurl4-openssl-dev libexpat1-dev libboost-filesystem-dev libboost-program-options-dev binutils-dev
wget http://www.lbreda.com/grive/_media/packages/0.2.0/grive-0.2.0.tar.gz
tar xvfvz grive-0.2.0.tar.gz
cd grive-0.2.0
cmake .
make
sudo make install
mkdir ~/google_drive
cd ~/google_drive
grive -a

grive
```
#### Adding Specific Files
```
git add --update 
will update or remove previously tracked files from the entire working tree. It will not add new files.

git add -A 
It will also update, remove previously tracked files, but it will also add new files.
```

#### REmove untracked Files
~~~
git clean [-d] [-f] [-i] [-n] [-q] [-e <pattern>] [-x | -X] [--] <path>…​

# Print out the list of files which will be removed (dry run)
git clean -n

# Delete the files from the repository
git clean -f
To remove directories, run git clean -f -d or git clean -fd
To remove ignored files, run git clean -f -X or git clean -fX
To remove ignored and non-ignored files, run git clean -f -x or git clean -fx
~~~


