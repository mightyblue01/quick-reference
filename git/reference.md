
### USER SPECIFIC
    git config --global user.name "xxx"
    git config --global user.email "xxx"

    git init
    (1) Add a remote repo locally 
    git remote add origin <URL.git>
    (2) Create a new branch
    git checkout -b new_branch
    (3) Pull into the new branch
    git pull origin master
    (4) 

    Examples- 
    (1) Clone an existing repo (ssh option)
        git clone git@ssh.dev.azure.com:v3/orgname/project-url
    (2) See all branches 
        git branch -a
    (3) Switch to other existing branch 
        git checkout develop
    (4) Checkout and create a new branch locally
        git checkout -b new-branch-name
    (5) Commit changes
        git config user.email "email.com"
        git config user.name "user name"

        git commit -m "commit comments" file1 file2     
    (6) Push the new branch to repo
        git push -u origin new-branch-name
    (7) Display commit history -
        git log
    (8) Revert to old commit -
        git revert commit_sha_value
--------------------------------------------------------------------------------------------
For a branch (Pull a new branch and push back with new file/s) ::
(Given that a branch already exists on remote Git)
git init
git remote add new_branch <URL.git>  
git pull new_branch new_branch
git checkout new_branch
<after creating a new file e.g. a.txt>
git add a.txt
git commit -m "message" 
git push new_branch new_branch


For a private repository :: 
git init
git clone -b <branch_name> remote_URL  :: using credentials => git clone -b <branch> https://usernmae@github.com/AGLEnergy/data-platform-etl-framework.git


git clone -b master https://username@github.com/xxxx/energy-insights-model.git


https://github.com/xyz/energy-insights-model/tree/energy-insights-docker

<add new files>
git add . or names
git commit -m "comments"
git push remote_URL <local_name>


git clone -b master https://user123@github.com/AGLEnergy/data-platform-etl-jobs-non-spark.git


git clone -b master https://user123@github.com/AGLEnergy/energy-insights-model.git

checkout a repo
clone a repo
branch a repo

add new files
commit files
push files

status 
difference

pull request
merge request


 (1) Generate the key 
    ssh-keygen -t rsa -b 4096 -C "email id" 
(2) Add to ssh agent 
    Start the ssh-agent in background - 
    eval "$(ssh-agent -s)"
    
    Add following in ~/.ssh/config 
    Host *
    AddKeysToAgent yes
    UseKeychain yes
    IdentityFile ~/.ssh/id_rsa
(4) Add the SSH private key to ssh-agent and store the passph
    ssh-add -K ~/.ssh/id_rsa
    
(5) Add the SSH key to github account

------
    
### Delete develop branch history 
    git checkout --orphan tmp-develop # create a temporary branch
    git add -A  # Add all files and commit them
    git commit -m 'Add files'
    git branch -D develop # Deletes the develop branch
    git branch -m develop # Rename the current branch to develop
    git push origin develop # Force push develop branch to Git server
