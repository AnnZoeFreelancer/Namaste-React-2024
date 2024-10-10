Pushing our code to Git
Go to git, create new repository.
Come back to terminal.  

We need to enter `git init` to make this repository as a git repository. 

Here our main branch in VS is master. You can see it bottom left of VS app.
Let us make our main branch as main. 
`git branch -M main`
This creates main as main branch. 

Create a readme file README.md

Let us push all these files to github
git add . 
This will add all these files. Then 
git commit -m "Ch-01-Inception"
Commit with a message.

Git is different than github.
Github is a place which hosts git repositories.

git remote add origin git@github.com:AnnZoeFreelancer/Namaste-React-2024.git
git push origin 
We are pushing our code to remote origin main branch 
git push origin main 
It will push all our codes to repository.

There is a public key privat key you have to set up SSH. Google it. 

"fatal: Could not read from remote repository.

Please make sure you have the correct access rights" 




