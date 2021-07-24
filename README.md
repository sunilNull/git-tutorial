# git-tutorial
* - init
    this command using once per repo when you create your repo
    > cd dir_name
    > git init ( after this create remote repo on github same name as dir_name)
    > git remote add origin <url>
* - setup username and email in your machin for git
    1) git config --global user.name "your name"
    2) git config --global user.email "your email"
-------------------------------------------------------------------------------
* - Clone
    description:
        using this command you can copy any online git repository
        to your local machine, and work with it, and agian you
        can upload it to remote.
    syntax:
        git clone repo_link
    example:
        git clone git@github.com:sunilNull/git-tutorial.git
-------------------------------------------------------------------------------
* - Status
    description:
        Get the status of your local repository.
        command tells you about how your project is progressing 
        in comparison to your remote repository.
    syntax:
        git status
    example:
        git status

* - Checkout
    description:
        if you want to create new branch u can use this command.
        or if you want to change between any existing branchs, you
        can simply use this command without '-b'.
        '-b' is indicating that you are creating new branch, which is not
        exist.
    syntax:
        git checkout -b branch_name
    example:
        git checkout -b sunil
-------------------------------------------------------------------------------
* - Branch
    description:
        using this command u can render all the branchs, which exist
        in current repository.
    syntax:
        git branch
    example:
        git branch
-------------------------------------------------------------------------------
* - Add
    description:
        if you have done any changes in your local repo,
        then you need to use this command.
        this command add changed/new created files in upload mode
        for git
        (if you want to add all the files/dirs then you can simply use '.')
    syntax:
        git add file_path
    example:
        'git add new_file.txt' or 'git add .'

-------------------------------------------------------------------------------
* - Rm
    description:
        A common question when getting started with Git is "How do I tell
        Git not to track a file (or files) any more?" The git rm command
        is used to remove files from a Git repository. It can be thought
        of as the inverse of the git add command.
    syntax:
        git rm files
    example:
        git rm *.py
-------------------------------------------------------------------------------
* - Restore
    description:
        if you add some files in commit mode. and you dont want to 
        add those files in your current commit. then you can use
        this basic command.
    syntax:
        git restore --staged file_name's
    example:
        'git restore --staged new_file.txt' or 'git restore --staged .' (if you want to remove all changes)
-------------------------------------------------------------------------------
* - Commit
    description:
        when you finalized your all the changes.and when you ready
        to upload your changes then you have to use this command.
        commit means you add one lognot/message for any perticular changes.
        simply its indicates that why you are changing this code(purpose).
    syntax:
        git commit -m "message_for_commit"
    example:
        git commit -m "learning to commit first time"
-------------------------------------------------------------------------------
* - Push
    description:
        this command use to update your remote repository with the current local dir changes.
        if you want to push forcefully you can use '-f', this will ignore all the errors and
        update/overwrites repo.
    syntax:
        git push repo_name branch_name
    example:
        'git push origin sunil' or 'git push -f origin sunil'
-------------------------------------------------------------------------------
* - Diff
    description:
        sometime you need to check whats the actual diffrance, or
        what we have changed in our current code.
        this command is basically used when multiple developer works
        on single project.
        we simply dont merge any branch's code to our main production code
        which migth broke current way. before merging any branch we have to 
        check it weather its right/good to merge or not. or this code is actually required or not.
        you can also compare two commits using its hash_code(found using git log)
    syntax:
        git diff branch_1 branch_2
    example:
        git diff HEAD~1 sunil
        git show hash_1 hash_2 ( shows changes between hash_1 and hash_2 commit, you can find hash from log)
-------------------------------------------------------------------------------
* - Merge
    description:
        if any developer had done his/her changes well.
        and those changes are ready to deploy in production server.
        then you need to merge that branch with your branch.
    syntax:
        git merge old_branch
    example:
        git merge sunil
-------------------------------------------------------------------------------
* - Pull
    description:
        if you hvnt work for some time, and other developer are works on that project.
        when you came back and willing to update some codes, you need to update your local repo
        with the newly update remote repo.
        by pull command you can achive this goal.
        if you do pull from another branch, then you should have to push it on your current branch also
        to make it updated.
        git pull is the more aggressive alternative; it will download the remote
        content for the active local branch and immediately execute git merge to
        create a merge commit for the new remote content
    syntax:
        git pull repo_name remot_branch_name
    example:
        git pull origin sunil

-------------------------------------------------------------------------------
* - Fetch
    description:
        You can consider git fetch the 'safe' version of the two commands.
        It will download the remote content but not update your local
        repo's working state, leaving your current work intact.

        if you want to Fetch all of the branches from the repository
        use ( git fetch repo_name )
    syntax:
        git fetch repo_name branch_name
    example:
        git fetch origin sunil

    after fetch you have to apply merge command which is shown below
        git merge origin/sunil
-------------------------------------------------------------------------------
* - Stash
    description:
        some time you need to pull or change branch to do some other stuff.
        but if you have changed your current files then its not good idea to
        loose all the changes. and do it again. for this problem we have stash
        this will store your unsaved(which is not added in commmit) in one place,
        from which you can rollback those changes and continue your remian work.
    syntax:
        git stash
    example:
        git stash ( if you want to save all the changes)
        git stash -u (if you also want to save untracked file)
        git stash list (to list out all the changes store in stash)
        git stash apply (to rollback changes in current branch)
-------------------------------------------------------------------------------
* - Log
    description:
        when you want to view your check all the changes done in project
        you can use log command. this is simple shows all the history of all the
        commit's of all the branches.
    syntax:
        git log
    example:
        git log (to simple show all the logs)
        git log --oneline (only show commit message history, along with branch name, hash)  
-------------------------------------------------------------------------------
* - Show
    description:
        to show changes between to commits.

        By default, git-show acts against the HEAD reference.
        The HEAD reference always points to the last commit of
        the current branch. Therefore, you can use git-show to display 
        the log message and diff output of the latest commit.
    syntax:  
        git show
    example:
        git show ( shows changes between current and previous commit)
        git show hash_1 hash_2(shows changes between hash_1 and hash_2 commit, you can find hash from log)
-------------------------------------------------------------------------------
* - Revert
    description:
        The git revert command is used for undoing changes to a repository's
        commit history. Other 'undo' commands like, git checkout and git reset,
        move the HEAD and branch ref pointers to a specified commit. Git revert
        also takes a specified commit, however, git revert does not move ref
        pointers to this commit. A revert operation will take the specified
        commit, inverse the changes from that commit, and create a new "revert
        commit". The ref pointers are then updated to point at the new revert
        commit making it the tip of the branch.
    syntax:
        git revert commit_hash
    example
        git rever hash_1
--------------------------------------------------------------------------------
* - Reset (avoid to use)
    description:
        The git reset command is a complex and versatile tool for undoing
        changes. It has three primary forms of invocation. These forms
        correspond to command line arguments --soft, --mixed, --hard. The
        three arguments each correspond to Git's three internal state
        management mechanism's, The Commit Tree (HEAD), The Staging Index,
        and The Working Directory        
    syntax:
        git reset
    example:
        git reset --soft "will reset commit_history"
        git reset --mixed "will reset commit_history and staged_snapshots" (changes removes from 'add')
        git reset --hard "will reset all the three tree(commit_history, staged_snapshots and working_dir)