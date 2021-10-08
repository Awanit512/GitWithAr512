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


#To check the status a handy command is 
git status
-------------------------------------------------------------------------------------------------------------------------------------------------------


# make some files and edit it by puting some useful contents of yr choice
touch first.txt

echo "Hell this is my first file of this begiiner Git Tutorials" >> first.txt


# To add files to stagging area :
git add filename

# To staged all the files at once
git add --a

# or 

git add .



# Finally to Commit
git commit -m "Initial Commit"	
