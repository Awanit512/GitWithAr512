GIT TUTORIALS BY AR512:

# to configure yours usernae and email
	git config --global user.name "Awanit512"
	git config --global user.email "awaitranjan000512@gmail.com"

# To see respected name or mail
	git config user.name
	git config user.email

# To list all the configurations 
	git config --list

# To set a particular editor   // to set vim or emacs
	git config --global code.editor vim  

# To see the config.editor 
	git config code.editor



-------------------------------------------------------------------------------------------------------------------------------------------------------
# To startr tracking initials yr directory/folder by git by below command (this will create a hidden folder names as .git We can see it by command   --> ls -a )
	git init   


# To check the status a handy command is 
	git status
-------------------------------------------------------------------------------------------------------------------------------------------------------



# make some files and edit it by puting some useful contents of yr choice
	touch first.txt

	echo "Hell this is my first file of this begiiner Git Tutorials" >> first.txt




### To add files to stagging area :  (PS:: note : git add is a multipurpose command which use for 
1> adding a modified file to a staging area as well as it also helps 
2> To add untracked files (ex: a newly created file ) to a staging area .)
command :

	git add filename

# To staged all the files at once
	git add --a

# or 

	git add .

# or 

		git add file1 file2 file3 file4 ..




### Finally to Commit (-m is for message)
	git commit -m "Initial Commit"



-------------------------------------------------------------------------------------------------------------------------------------------------

### To track or see log
	git log

-------------------------------------------------------------------------------------------------------------------------------------------------



## to remove git repo local
	rm -rf .git

### To clone a remote repo say --> https://github.com/remote_repo/remote_repo.git  (this is a fake url)
	git clone https://github.com/remote_repo/remote_repo.git 	



----------------------------------------------------------------------------------------------------------------------------------------------------------------



### Git ignore : Helps to ignore some files or not to track those files

	touch .gitignore

# and now put names of the files which u didn't want to track in .gitignore so whwnver u add a name of file in .gitignore and suppose made a change in files which is listed in .gitignore then any changes done to those files will be ignored, but yaeh only .gitignore will be modifed as git do tracks .gitignore directory so we have to staged that and commit it.

examples of names/files in .gitignore  (all files names with extension .logs will be ignored it can be in any subdirs too still it will be ignored, error.log will be ignored, all files inside dir directory( this dir directory can be presnt in any subdirectory of root foler of our project but still it will be ignored by git ) will be ignored.)
Note: : the /dir/ directory states that to ignore the directory named as dir in root folder of our project.

### PS:: git by default ignores the blank directory.
*.logs
error.log
/dir/
dir/    


----------------------------------------------------------------------------------------------------------------------------------------------------------------


## Git diff  : Calculates the diff between unmodified files in staging area and modified files in working directory.(ex:: i staged the file say readme.md after that i modified the same file then readme.md will be in both -> Staging area ( Changes to be Committed ) as well as in -> Changes not staged for Commit. 

	git diff

# To comapre previous commit with staging area of now :
	git diff --staged

----------------------------------------------------------------------------------------------------------------------------------------------------------------



# Skipping the staging area (so yeah we can commit the tracked modfied file directly with adding into staging area explicitly by single command)

	git commit -a -m "skiiping satging area and commiting directly"

PS:: suppose u have created a new file by say touch new_file.txt then as it will be untracked so using above command i.e git commit -a -m "any suitable commit message here"  will not commit the untracked file this command will commit only tracked modiied file. for untracked u have to use command git add new_file.txt in order to make it tracked after that u can use above command to directly commit it skipping the habit of adding files to staging area explicitly. 


PS :: :: Note the -a flag helps to add files to staging area implicitly after that it finally commit it.  


----------------------------------------------------------------------------------------------------------------------------------------------------------------



## Moving and Renaming files in git

note :: we can remove the files by simply deleting it or renamed it (f1.txt --> g1.txt ) say  by use of GUI but in this case later the git status shows a new file  (g1.txt ) which is -->untracked  which i use to renamed the older file (f1.txt ) and also show the status of older file (f1.txt) which i renamed  as deleted.
But yeah once we add it to staging area by git add . then it shows the right message i.e renamed : f1.txt to g1.txt

so instead of deleting in this way bettwe to delete via git as changes such as renaming and deleting are automatically staged so just need to commit.


# To delete: 
	
	git rm f1.txt
	where f1.txt is the name of file to be deleted.



# To Rename: 
	
	git mv f1.txt g1.txt
	where f1.txt is the renamed to g1.txt.

	Now we just need to do git commit -m "" in order to commit the new chaneges.




#####################################3########### IMP #############################################

## Suppose we made any tracked file say first.txt into .gitignore and commit it by git commit -a -m "make firt.txt to ignore by git"
 then after modiftying first.txt it still get reflected in git status 
logically :: it should not be there as we already listed it into .gitignore so it shoud stop tracking it but No , it will still track it because since we have keep the name of file in .gitignore which earlier was getting tracked by the git so we have to tell explicitly to git not to track by the command

	git rm --cached first.txt  

Note this command will not delete the file but rather stop tracking it, so now it can be sucefully ignored by the git .
But Note upon typing git status it will list :

Changes to be commited:    <--------- (this line because we used git in front of git rm --cached first.txt so no need to add changed to staging area already staged and is ready for commit)
    deleted : first.txt    <------- IT to be noted here we have just make git not to tracked but it list deleted

    We just need to commit our change again do git status we will find tree is clean.

    So,the aboe command just untracked the file .

    SO a Q: Wgy git status does not show that file first.txt as untracked
    Ans : Because , we had put the name of the file in .gitignore So, obviously if we don't put that in .gitignore then obviously it will listed as untracked .


    So this is a way to untracked a file 
    Q: WHAT IF WE want to track it again ?
    Ans: if file is not listed in .gitignore then simply git add that_filename or else
    first remove its name from .gitignore 

	 



## To untrackded a file say : jj.txt

	git rm --cached jj.txt

# To make it trakc again (jj.txt)
	git add jj.txt
	git commit -m "making jj.txt is gtting tracked now."





## Git LOgs: Viewing and changig Commits in Git .

	git log  // to view the commit 
	git log -p //  shows the diff value (whatever things removed or added in the commit )
	git log -p -2 //  shows the diff value (whatever things removed or added in the commit ) for only first two commits.

	git log --stats // gives information of just showing no of changes addition or subtraction/deletions in each files. i.e short summary of nuber of changes followed by number of additions and number of deletions.

	git log --pretty=oneline   //show all commits in one line

	git log --pretty=short    //show all commits in short detailing commit hash id, Author and commit message 

	git log --pretty=oneline   //show all commits in full detailing commit hash id, Author, Committer and commit message 	

	## time filter logging

			git log --since=n.seconds   // n or 2 can be subituted replaces respectively by  some other number

 			git log --since=n.minutes
			git log --since=2.hours
			git log --since=2.3.days

			git log --since=2.years
			git log --since=2.months
			git log --since=2.weeks
			git log --since=2.days



	# Different format in pretty   check in git log on internet 

		git log --pretty=format:"%h -- %an" // hash commit -- author name ---> "%h -- %an"
		git log --pretty=format:"%h -- %ae" // hash commit -- author email-->  "%h -- %ae"


--------------------------------------------------------------------------------------------------------------------------------------------------------------


## If want to commit your changes into previous commit 

	git add . 
	git commit --amend   // amend means minor chanegs in just previous commit.


## To make a staged file to unstaged 

	git restore --staged <filename>

## To Unmodify a File: Suppose you modified a file named first.cc now u want to restore the previous vesrion:

	git restore first.cc

###  or 

	git checkout -- first.cc


# Note PS:: the 'git restore' compares working dir changes to its  nearest one i.e staging area or .git repo if ur file is not in staging area as it not yet staged then on restoring it will checkout to previous commit changes else if its staged then only non staged changes of that  file will be removed leaving behind staged chanegea
 for removing staged changes too two ways:

 	1> firt make the file unstaged by 'git restore --staged <filename>' after that 'git restore <filename>'
 	2> [ NOT RECCOMENDED ]   git checkout -f // straightforward leads to previos commit dangerous if u dont want to reached to preivios commit state for other files . 


--------------------------------------------------------------------------------------------------------------------------------------------------------------

## supoose mny changes have been done and now don't want to commit these changes but rather want to go back to previous / or wnat to restore the previosu commit

	git checkout -f

	
--------------------------------------------------------------------------------------------------------------------------------------------------------------


## Git :: Working with remote repositories. 

	git remote add origin https://github.com/Awanit512/GitWithAr512.git  
	// meaning this command add remote URL https://github.com/Awanit512/GitWithAr512.git   (this is for github we can siliarily go for gitlab) by name as a origin.  here instad of origin we can keep other name such as git remote add MAINORIGIN https://github.com/Awanit512/GitWithAr512.git  but its feneral parctise to say that as origin

	Note :: It is recommended to use ssh url for pushing as -->Support for password authentication was removed on August 13, 2021 so git will tell you to  use a personal access token instead. For setting this :



					--------------------------------------------------------------------------------------------------------

	^^^^^


	Follows Following steps :
			>>> ssh-keygen -t ed25519 -C "your_github_email_here.com"  
			 //This will generate private/public key pair 

			>>> eval "$(ssh-agent -s)"
			>>> ssh-add ~/.ssh/id_ed25519
			>>> tail ~/.ssh/id_rsa.pub
					Now in the output copy the key and Go To github repo in which you want to push 
					Go to settingd-->
					 				Deploy Krys-->	
					 								Add Deploy Key-->	
					 													Give the Titile and paste the key in Key TextArea which u copied from the terminal.  
			After thta changes can be easily pushed to yrs repo.

					--------------------------------------------------------------------------------------------------------







	git remote
		o/p-->origin

	git remote -v
		o/p-> origin	https://github.com/Awanit512/GitWithAr512.git (fetch)
		      origin	https://github.com/Awanit512/GitWithAr512.git (push)






	git branch -M main   // by default its main if this step is skipped thne git implicitly do this 
							--> Branch 'main' set up to track remote branch 'main' from 'origin'.




	git push -u origin main

		Enter urs username and Password if promplted  : to push yr changes to github repo. ( remember the password is that ssh deploy key. if forgot then set up the new one by following same step as detailed above in ^^^^^)


------------------------------------------------------------------------------------------------------------------------------------------------------


 Suppoose u want to remove the exsting origin URL then

	git remote remove origin

Now u can add any other origin URL by 'git remote add origin <url>'

	                 OR

Above both steps for acheving goal( i.e changing origin url to something else )can be done by following command:

	git remote set-url origin <required_new_url>


------------------------------------------------------------------------------------------------------------------------------------------------------





## Git ALiases it helps to write just a short command for the long commands by aliasing those commnads.
	
examples we suppose want git st t perform same as git status we can do this by :

	git config --global alias.st status

	Now 'git st' is same as 'git status'


now lets commit by git cmit by 


	git config --global alias.cmit commit

	Now both git commit -m " " is same as git cmit -m " "


Now lets make a alias for unstaging the file say f1.txt

	git config --global alias.unstaged 'restore --staged'

	Now git restore --staged f1.txt is same as git unstaged f1.txt


Now lets make another alias for checking last commit and last two commits :

	git config --global alias.last 'log -p -1'

NOW, git log -p -1 is same as git last 

and 

	git config --global alias.last-two 'log -p -2'

NOW, git log -p -2 is same as git last-two


Lasly To remove the aliases : (suppose we wan't to remove alias.last-two then do following: )

	git config --global --unset alias.last-two

	If it's local then don't give the --global flag i.e 'git config --unset alias.last-two'

	This way doing seems safer than ediiting config file by : --> 'git config --global --edit'

----------------------------------------------------------------------------------------------------------------------------------------------------------------


### ------------------------------------------------------------------------IMPORTANT-------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------



## Git Branching and Switching  


in order to make a branch type following : 	

	git checkout -b develop   // where develop is the branch name   here this command create a new branch by -b flag and chekcout to new branch.


	Difference between git checkout and git branch 


	git  branch <new-brach-name> :-  creates a new branch but stays at existing branch.
	git checkout -b <new-branch-name> :- creates a new brahc and check in to new barnch. 


	git chckout -b <branch-name> == git branch <new-branch>
									git switch <new-branch>

									or

									git branch <new-branch>
									git checkout <new-branch>


	# To list all the BRANCHES:

		git branch 



	# To move to some branch say dev

		git checkout dev

		or

		git switch dev



----------------------------------------------------------------------------------------------------------------------------------------------------------------


## Merge Conflict/ Merging 

assume we are in main branch

	git merge tryFeature


## Merge Conflict 
whenever mege conflict arises it starts with a 'conflict resolutio marker' 

	<<<<<<< HEAD   and end with >>>>>>> tryFeature   assuming conflict is between brancehs HEAD (main) & tryFeature
	and code part which creates conflict between both branches is seperated by =======  .
 
	example:
			<<<<<<< HEAD
			    <h1>Hi THis is Awanit512 </h1>
			=======
			    <h1>hello WORLD!!!!!!!!!!!!!!!</h1>
			>>>>>>> tryFeature 

For resolving it either kep both or Imcoming Changes( changes of tryFeature branch) or keep changes Current branch (i.e of main branch) 



--------------------------------- Branch Management ---------------------------------------------------------


To list all branches(* shows currently we are in which branch )

	git branch

To show all branches with last commit's commit hash id and commit message 

	git branch -v

	o/p:	  develop    cc2b884 Monster Video removed
			* main       fc1ab0f merged
			  master     1170d3e [ahead 1, behind 9] nothing much
			  tryFeature c755a89 hello world


To show all the branches which are merged :

	git branch --merged



To show all the branches which are  not yet merged :

	git branch --no-merged

To delet a merged branch (else if it is not merge then it will throw a error with warning)

	git branch -d tryFeature    
		//(as tryFeature is already merged in main.) like this :
			error: The branch 'develop' is not fully merged.
			If you are sure you want to delete it, run 'git branch -D develop'.



If you are sure you want to delete it even if the brach (say develop) is not merged yet then, run:

	 git branch -D develop

	 i.e 

	 git branch -D <branch-name>

	



----------------------------------------------------------------------------------------------------------------------------------------------------------------




## Branching WorkFLOWS:



We generally make two types of branches:

1>Long Running Branches : long lived span of life of these branches is long exmaple master, develop, system, propose change

2>Topic Branches : plugin change, etc.



# Now Pushing branch to remote repo


	git push origin <branch-name>   // It is good practised to be locally on same branch to which u want to push

if we want at remote to have this branch as some other name then we can do so by this way :

	git push origin <branch-name>:<branch-remote-new-name>

		ex :(assmuing we are in branch mybugfix and want to push it but named it there on remote as just bugfix)
			git push origin mybugfix:bugfix

If we want to delete the branch locally : 

	git branch -d <branch-name>  // assuming it alreayd merged else thorw an error. if still want to delete it then 
		git branch -D <branch-name>

if we want to delete the branch in remote say on github :

	git push -d origin <branch-name_to_delete>


---------------------------------------------------------------------------------------------------------------------------------------------------------------  

----------------------------------------------------------------------------------------------------------------------------------------------------

<h1>Bye</h1>

