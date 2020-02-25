Breaking Git 

## My TOP 50 adorable git commands
#### Setting up your user profile for a specific repo  
1. git init/clone # Is your magical starting point of any repo
2. git config --global user.email "your_email@example.com" # Simple but very core to a workflow
3. git config --list  # View "your profile" as the repo user. Its a per machine basis

#### Work in progress 
4. git reset HEAD <file-name> # Rollback changes at commit or when stagedstaged 
5. git tag 		      # List out existing tag of your commits. Branch specific !!
6. git tag -a -m "Version 1 tag" v1.0	# Annotated tags 
7. git tag v1.1-lw	      # Lightweight tag 
8. git branch -m demo1 demo2 # rename branch
9. git pull # fetch and merge 
10. git fetch # get from origin, no merge
11. git diff mater demo_branch # do ths while in master branch, gives u diff of both branches 
12. git log --one-line --decorate --graph --all # graphical view all branches
13. git config --global credential.helper store # Set creds for specific repo ; followed byt git pull 
14. git config --global --unset credential.helper # Unset credetials for specific git repo 

## Funky git customizations  
Review custom bash prompts for git
Checkout source tree(bitbucket) desktop client

## Git Squash all commits 
Steps to squash 
after all changes 
    1. git add -all --- as usual
    2. git commit -am "comments" --- as usual
    3. git push origin local_branch 
        -     - git log --oneline 
    4. git rebase --interactive YOUR_FIRT_COMMIT_HARSH
        - git log --oneline 
    5. In vim %s/pick/squash/pick/g 
    6. Change the top first line in VIM to pick 
    7. Another vim opens here, and you need to comment out all crazy comments
    8. Have one single comment that describes your work 
        - OutPut: [detached HEAD 5b6ef70] POD-2436: Final clean up s3 module - With base public policy
                    Date: Mon Feb 24 14:32:49 2020 +0000
                    6 files changed, 81 insertions(+), 9 deletions(-)
                    create mode 100644 s3_bucket/README.md
                    create mode 100644 s3_bucket/data_source.tf
                    create mode 100644 s3_bucket/provider.tf
                    Successfully rebased and updated refs/heads/feature/POD-2436.
    9. git log to see how things are looking 
    10. At this poit all squash has happened locally 
    11, push squached commit to remote branch 
        - git push origin branch_name -f 
