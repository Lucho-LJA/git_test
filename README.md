# Git Test
practice of git cmmands with Odin project. The steps was done with `PowerShell`.
## Basic Comands
the file [Hello world](src/hello_world.txt) is used to probe the comands basic with the nexts instrcuctions.
- Following the instruction about basic GIT in Odin Project
- Create a repository in GitHub with any name (git_test)
- Use a terminal to clone the repository with the command: `git clone git@github.com:Lucho-LJA/git_test.git` using the `SSH Method` explained in Odin project in the section about basic use of GIT
- Locate in root folder that was cloned
- Create a file named `hello_world.txt` and add any information Eg.(Hello <your name>!).
- Add all changes with: `git add .`.
- Commit the changes with: `git commit -m "message abput changes"`.
- Push the change to GitHub: `git push origin main`.

## Depper look at GIT
create 4 files: `New-Item testn,md - type file`. n represent 1,2,3,4.
### Changing The Last Commit
- To uddate repositories running the commands:
<!--sec data-title="Command: Windows" data-id="windows_git" data-collapse=true ces-->
    git add test1.md ; git commit -m "Create first file"
<!--endsec-->
<!--sec data-title="Command: Windows" data-id="windows_git" data-collapse=true ces-->
    git add test2.md ; git commit -m 'Create send file' 
<!--endsec-->
<!--sec data-title="Command: Windows" data-id="windows_git" data-collapse=true ces-->
    git add test3.md ; git commit -m 'Create third file and create fourth file'
<!--endsec-->
- With the last command we forgot to add test4.md, so the solutiion is:
<!--sec data-title="Command: Windows" data-id="windows_git" data-collapse=true ces-->
    git add test4.md
    git commit --amend
<!--endsec-->
Note: This action replace the last commit, so you only use it if it wasn't pushed.
### Changing Multiple Commits
- If we want to change some commit, use the comand `rebase -i`. To change 2 last commits run:
<!--sec data-title="Your first command: Windows" data-id="windows_whoami" data-collapse=true ces-->
    git log
    git rebase -i HEAD~2
<!--endsec-->
- After select the options you can run the next comand to change the commit with `edit` option and finish all with the last comand.
<!--sec data-title="Your first command: Windows" data-id="windows_whoami" data-collapse=true ces-->
    git commit --amend
    git rebase --continue
<!--endsec-->
### Squashing Commits
- To squash the commit "create second File", run:
<!--sec data-title="Your first command: Windows" data-id="windows_whoami" data-collapse=true ces-->
    git rebase --root
<!--endsec-->
- Change the option commit "create second File" from pick to squash
- save and exit
- Wriite the new commit message with "Create first and second file"
- save and exit and that's all
### Splitting Up a Commit
- run:
<!--sec data-title="Your first command: Windows" data-id="windows_whoami" data-collapse=true ces-->
    git rebase -i HEAD~2
<!--endsec-->
- Change the option pick to edit of commit "Create third file and fourth file"
- run:
<!--sec data-title="Your first command: Windows" data-id="windows_whoami" data-collapse=true ces-->
    git add test3.md ; git commit -m "Create third file"
    git add test4.md ; git commit -m "Create fourth file"
<!--endsec-->
- exit rebase:
<!--sec data-title="Your first command: Windows" data-id="windows_whoami" data-collapse=true ces-->
    git rebase --continue
<!--endsec-->
- See the new commits with: `git log`