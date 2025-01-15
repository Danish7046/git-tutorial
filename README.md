STEP: GIT INSTALLATION
       
       STAGES:
       U - UNTRACKED
       A - ADDED OR STAGED
       C - COMMITED
       M - MODIFIED
       
STEP: DO SOME STUFFS TO SET OUT INFO TO GLOBALLY TO KNOW WHO DO OR WHEN THEY DO SOME UPDATES/CHANGES

       (1).first we have to set username globally when we start our first git&github 
           which shows how much contribution we track at any particular project:
                    git config --global user.name "Danish Badhra" 

       (2).Same as above we have to set email globally:
                git config --global user.email "badhradanish4925@gmail.com"

       (3).When we arise some problem in our project the following command helps to figure out what the problems we arise:
                git config --global core.editor "code --wait"

       (4)The below command helps when the group member works on different system to figure out 
          the last line will set automatically when one works on mac other were on windows the space set automatically:
                git config --global core.autocrlf "input"

       (5)when we want to edit any input the below command will be use:
                git config --global -e

STEP: MAKING GIT AVAILABLE IN OUR PROJECT 

STEP: MAKING A CHECKPOINT OR SAVE POINT 
        -adding file
        -staging them
        -commiting them

        git log --oneline => to know current status of saved points
    
STEP: GOING BACK TO SOME PREVIOUS SAVED POINTS
        logging everything
        reverting back to the previous saved point
        git reset --hard HEAD~1 => to revert back to any saved points 
        git status -s => to know about which files was in which mode means in staging,tracked,untracked,modified,etc
          |       
        NOTE: only show status which file are commited or after commiting they are in modified stage

        git log --oneline => to know how many check points are 
        git log --oneline --graph ==>this will use when we branched and 
                                     conflict occur so where our branch break and then merge show the path
        git log => show all histories(all commit/status)

STEP: BRANCHING 
       git branch feature/navbar => for creating branch 
       git branch => for showing all branch
       git switch feature/navbar => if we want to move to required branch
    
STEP: TYPES OF MERGING:-
       (1) three way merge :-when there are 1 or more line of code in main and branch so when we add 1 or more 
                             line of code in main and branch then when we commit both we got conflict after 
                             solving we got a path where it broke and show the path using command 
                             NOTE : git log --oneline --graph

                             Here we have handle a conflict

           git merge feature/navbar

       (2) fast forward (ff) merge :-

                                  here simply we only change the position of head means when we make a clone 
                                  of main and make changes or add some stuff and then we just move the head to 
                                  main to the respective changes file 
           
       (3) squash merge
       (4) recursive strategy merge
       (5) rebase merge
 
        NOTE : git branch -d feature/navbar => to delete any branch

STEP: STASHING :- If you write something without commiting it and if you want to try to move to some 
                  other branch then git figure out us that there is added any stuff or simply you have 
                  not created a checkpoint and it may cause we should delete the stuff or draft the code but 
                  this draft never add or delete but in between they where put in any when we move to that branch
                  we used it 
                
                NOTE: git switch -C feature/add-footer => this command also create new branch and switch to that 
                                                          branch so 2 step in 1 step 

                git stash => when we write in some file and switch to some other branch it cause what we do 
                             to the previous works you not done it add/commit and we do stash so it would 
                             store in there memory temporary and we see what we need and again back to that file
                             and do 
                git stash apply => the previous draft work comes back 

                first we => git stash 
                second => git switch feature/add-footer => switch to any branch and see the code or 
                          see what stuff we want to see
                third =>  git switch main => switch to main
                fourth => git stash apply

STEP: first 1 main person create folder the required file and create new repository and add it 

      echo "# testingtest" >> README.md
      git init
      git add . =>for all file upload or git add README.md 
      git commit -m "stage0"
      git branch -M main
      git remote add origin https://github.com/abc/testingtest.git
      git push -u origin main 
    
      Other person after collbration:-

            git clone https://github.com/abc/testingtest.git when other wants to make change in code
            git switch -C feature/add
            do what stuff you want 
            git add . =>for all file upload or git add README.md 
            git commit -m "stage0"
            git push -u origin feature/add

      After complete Main person fetch and merge the updated code:
           
            git fetch
            git switch main
            git merge feature/add -> branch name

            git push -u origin main => to upload to github so all collabrator can see 

      Other person:
            git switch main
            git fetch
            git pull
            
