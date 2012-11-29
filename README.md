1. fork, clone, make a change, and publish it

    ````bash
    hub clone marshally/git_workshop_examples
    hub fork
    # edit a file
    # let's add some text from http://www.ipsum-generator.com/loremipsum/paragraphs to index.html
    # check it in
    git add .
    git commit -v
    # push it up
    git push
    ````
    
2. merge in changes from branches safe_merge and this_branch_will_cause_a_merge_conflict

    ````bash
    git diff safe_merge
    # that was easy, what about a conflict?
    merge conflicts
    git merge this_branch_will_cause_a_merge_conflict
    # oops, let's back out
    git reset head --HARD
    # let's look ahead and see what the problem is
    git diff this_branch_will_cause_a_merge_conflict
    git merge this_branch_will_cause_a_merge_conflict
    # fix merge error
    git add index.html
    git commit -v
    ````
    
3. create your own branch and add some beautiful styling

    ````bash
    git branch add_beautiful_styling
    git checkout add_beautiful_styling
    #  or
    git checkout -b add_beautiful_styling
    # edit some files, add some styles
    git add .
    git commit -v
    # set up a tracking branch
    git push origin add_beautiful_styling
    git branch --track add_beautiful_styling origin/add_beautiful_styling
    ````    

4. pull in changes from origin/master

    ````bash
    git checkout master
    git pull
    git checkout add_beautiful_styling
    git merge master
    ````
    
5. create a pull request, leave some comments, and accept it

    ````bash
    hub compare
    hub pull-request
    ````
    
6. tagging

    ````bash
    git tag v1.0.0
    git branch hotfix_remove_user_account
    # do 3 commits
    git checkout master
    git cherry-pick hotfix_remove_user_account^
    ````