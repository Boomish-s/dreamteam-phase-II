I have learned somethings related to git those includes:

											
STEP:1 
		GO INTO/CREATE FOLDER 
			
		SET THE DEFAULT BRANCH INTO MAIN (not master) AND INTIALIZE
			git config --global init.defaultBranch main
			git init 

STEP:2
		GIVE THE DETAILS OF YOU USING 
			 git config —global user.name “x_y_z” like wise email also you should give
            git config --global user.email "email "

STEP-3:

		CREATE A REPO IN GITHUB USING GUI AND COPY ITS LINK 
		CONNECT BOTH USING 
				git remote add origin <link>

STEP 4:
 		DO THE CHANGES / CREATE FOLDER STRUCTURE IN YOUR IDE AND CODE ACCORINGLY 
STEP_5:
		ADD THE EVERY CHANGES  USING
						git add . 
		COMMIT USING 
						git commit -m “added x_y_z”
		PUSH  INTO GIT BY :
						git push -u origin main
                 here main means the main branch which is initial
                   if you want to push to another branch use the spefic branch name  
                              

											
CHECKING WHAT IS CURRENT STATUS:
					git status
					it give the current status of the git ,and say if some uncommitted files and etc ..
LIST OUT ALL THE COMMIT:
				git log 
				it lists out all the commits with an specific id at the end which used to check the specific  change later on…
TO CHECK/VISIT  A SPECIFIC COMMIT :
				git checkout id
				copy the specific id from git log and paste here , we would get the entire details of those commit 
				it only show the info, files and etc which was existing at the time of that commit 
				note :
					once the thing done and you wanna come to the latest or main branch 
					use : git checkout main 
					or you will be in the older state 
IF YOU MADE ANY CHANGES IN PREV COMMIT :
					IF YOU WANT THOSE CHANGES:
						create a new branch and you add ,comit and push 
						don't just push or add or commit 
						create a new branch and do those stuffs 
					IF YOU DON'T WANT THOSE CHANGES:
						git checkout -f main
												BRANCHING
CREATE A BRANCH:
			git branch <branch name>
MOVE TO A BRANCH:
			git checkout <branch name>
TO CREATE AND MOVE TO A BRANCH :
				TO DO BOTH AT A TIME:
						git checkout -b <branchname>
SOURCE BRANCH:
  WHILE CREATING A BRANCH — CHECK WHERE ARE YOU CREATING IT 
  THE BRANCH WILL BE CRETED ON THE BRANCH YOU ARE 
FOR AN EX:
		IF YOU CREATE A BRANCH BUG IN MAIN AND SUDDENLY CREATE A NEW BRANCH CALLE FEAUTRE 
		THRE STRUCTURE WOULD BE 
				MAIN—|	
					     |-BUG
							|-FEAUTRE 
		IF U WANNA CRETE BOTH PARALLEL TO MAIN 
		CREATE A BRANCH AND AGIN COME TO MAIN AND CREATE AGAIN 
CREATE A BRANCH FROM A SPEFIC BRANCH:
				git branch <new_branch_name>  <the_existing_branch>
				this used to create a branch from a septic branch 
				usually the branch creates from in which branch we exist
				this is useful for specific case

PUSHING THE BRANCH TO GITHUB—(UPSTREAM):
				This is called UPSTREAM (pushing the local branch to the GitHub )
				git push -u origin <branch_name>
					OR 
				git push —set-upstream origin <branch_name>
				both does the same work 
				use the first syntax to make the process easier 

PULL REQUEST:
	It is the request to merge the changes into the main or a specific branch 
	USE GUI for this it is the best practice 
	go to pull request option ,select the branches to merge ,add a commit message and give pull request 
	pull request Is a request to merge two branches 

										RESOLVING MERGE CONFLICT 


		First 
		push the contents of main to the present branch
		then resolve the conflicts using gui 
		again push back to main 

		I,e
			main —-> specific branch
			resolve the conflict 
			specific ——>main

		RESOLVE IT USING GUI 
			THERE WILL BE FOUR OTPION ACCORDING TO THE EDITOR ,CHOOSE ONE ACCORDING TO THE SITUATION
			AFTER DOING THAT—— AGAIN PUSH BACK TO MAIN
        STEPS:
                git checkout -b "specific branch" -----> go to specific branch 
                git merge main --------> push the contents of main to specific branch
                resolve conflict by gui ,with those 4 specific options 
                git add .    ---> stages all the changes 
                git commit -m "commit mesage" ----> commits the change                    
                
			
										                            GIT - RESET 
Take the case of revisting the older commits 
while you revisiting if you wanna the older (ie revisted code) 
you wanna use git reset function ,BUT the commits after that is delete

HOW TO USE:
            git reset <uid>

where uid means the id of the specific commit , get the uid from git log 
            git reset is used to move and go back to the older code 

NOTE:
        THE COMMITS AFTER THE SPECIFIC COMMIT(STEP) GETS DELETED PERMANENTLY

after that dont forget to stage and commit:
            git add .
            git commit -m "commit message"

            
													       GIT - REVERT

IT IS SAME AS GIT RESET 
BUT IT TAKES PLACE WITHOUT DELETING THE NEXT COMMITS 
AND THE COMMMIT WHICH WE GO BACK IS ALSO ADDED AS A NEW COMMIT 

EX:
A->B->C->D
IF YOU GO BACK TO B USING GIT REVERT 
A->B->C->D->E , WHILE E IS THE STEP OF GOING BACK TO B

WHEREAS IN GIT RESET 
IF YOU WANNA GO BACK TO B IN A->B->C->D
 THE COMMIT WILL BE A->B

WHEREAS THE C AND D GOES OFF
  

        git revert <uid>



												GIT-STASH
GIT STASH IS USED TO STOP OR HOLD THE WORK while we work in a unprior task 

let us assume you are working in a unpriority task ,like studing holy books during mid-sem ,now you wanna stop and continue studying math for the mid sem, and you dont want to add or commit because the task in unfinised to do those,
In that case to hold or stop the process we use git stash 

syntax:
        git stash 
 
nothing more just git stash 
which halts the current process
