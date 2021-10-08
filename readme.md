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



## Git diff  : Calculates the diff between unmodified files in staging area and modified files in working directory.(ex:: i staged the file say readme.md after that i modified the same file then readme.md will be in both -> Staging area ( Changes to be Committed ) as well as in -> Changes not staged for Commit. 

git diff
