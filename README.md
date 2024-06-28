# DZ_June
Changes from Tamila Mumdghi
First, create a new local branch and check it out:

git checkout -b <branch-name>
The remote branch is automatically created when you push it to the remote server:

git push <remote-name> <branch-name> 
<remote-name> is typically origin, which is the name which git gives to the remote you cloned from. Your colleagues may then simply pull that branch.

Note however that formally, the format is:

git push <remote-name> <local-branch-name>:<remote-branch-name>