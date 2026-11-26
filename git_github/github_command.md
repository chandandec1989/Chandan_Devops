### VENV:-
python3 -m venv venv =  create VENV
source venv/bin/activate = linux activation
venv\Scripts\activate.bat = window activation
.\venv\Scripts\Activate.ps1 = window Powershell
deactivate = deactivate

### GIT & GITHUB:-
• Git & GitHub Command:-
1. Repository & Setup Shortcuts:-
        i. Git init                               --     initialize new repository
        ii. Git clone <url>                       --     clone a repository
        iii. Git status                           --     Check status of files
        iv. Git config --global user.name "Name"  --     Set global user name
        v. Git config --global user.email "email" --     Set global email
        vi. Git config --list                     --     To verify config list

2. Basic workFlow Shortcuts:-
        i. Git add .                              --     Add all changes
        ii. Git add <file>                        --     Add specific file
        iii. Git commit -m "Message"              --     commit chnages
        iv. Git commit -am "Message"              --     Add and commit (Tracked files)
    V. git remote add origin https://github.com/chandandec1989/Kong_api_gateway.git
       --  first time need to connect the git repo
    vi. git push -u origin master             --     push change to remote
        vii. Git push                             --     Push changes to remote
        viii. Git pull                            --     Pull latest changes

3. Branching Shortcuts:-
        i. Git branch                             --     List all Branches
        ii. Git branch <name>                     --     create a new branch
        iii. Git checkout/switch <name>                  --     Switch to a branch
        iv. Git checkout -b <name>                --     Create and switch to new branch
        v. Git merge <branch>                     --     merge a branch
        vi. Git branch -d <name>                  --     delete a branch

4. Undo & restore Shortcuts:-
        i. Git restore <file>                     --     Discard changes in a file
        ii. Git restore .                         --     Discard all changes
        iii. Git reset <file>                     --     Unstage a file
        iv. Git reset --hard                      --     Reset everything(***Be careful***)
        v. Git revert <commit>                    --     Undo a commit(safe)
        vi. Git clean -fd                         --     Remove untracked files & Folders

5. Stash Shortcuts:-
        i. Git stash                              --     Stash current changes
        ii. Git stash list                        --     view stashes
        iii. Git stash apply                      --     Apply latest stash
        iv. Git stash pop                         --     Apply and remove latest stash
        v. Git stash drop                         --     Delete a stash

6. Remote Repository Shortcuts(GITHUB):-
        i. Git remote -v                          --     View remote URLs
        ii. Git remote add origin <URL>           --     Add remote repository
        iii. Git push -u origin <branch>          --     Push and set upstream
        iv. Git fetch                             --     Fetch latest changes
        v. Git pull origin <branch>               --     Pull from the specific branch
        vi. Git push origin --delete <branch>     --     Delete remote branch

7. Useful shortcuts:-
        i. Git log --online                       --     View commit history (short)
        ii. Git log --graph                       --     view commit history (graph)
        iii. Git diff                             --     show changes
        iv. Git show <commit>                     --     show commit details
        v. Git blame <file>                       --     see who changes a line
        vi. Git bisect                            --     Find the commit that introduced a bug

8. To merge local master into feature/chandan_code, switch to the destination
   branch and merge:
    i. git switch feature/chandan_code        -- first switch the traget branch
    ii. git merge master                      --
    iii. git rev-parse master                 --

9. In Nano:
    i. Press Ctrl+O to save (“Write Out”).
    ii. Press Enter to confirm the filename.
    iii. Press Ctrl+X to exit.