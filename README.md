# Git 101

## DevOps 101 - Introduction to Git

In this lab we will be taking a look at git source control management as well as how we can use GitHub to store our projects.

### Prerequisites

* A GitHub account

### Configuring your git cli

1. Open up your web terminal instance by navigating to the address given to you. It should look like [http://oliver-workshop-terminals.us-east.containers.appdomain.cloud/termXX](http://oliver-workshop-terminals.us-east.containers.appdomain.cloud/termXX).
2. Navigate to the _data_ directory by using the following command

   ```text
   cd data/
   ```

This directory that we just changed into has the permissions that we need to run the commands for our labs today. Be sure that all of the work that you are doing resides within this directory.

1. Now we need to configure our Git cli to authenticate with our GitHub account. In the terminal, enter the following command replacing _your\_username_ with your GitHub username.

   ```text
   git config --global credential.https://github.com.username your_username
   ```

2. Then run the following command to have your username added to commit messages going forward. Replace _your\_username_ to your own GitHub username:

   ```text
   git config --global user.name "your_username"
   ```

![git username](.gitbook/assets/gitusername.png)

1. Then, enter the following command replacing _your\_email_ with your GitHub email address.

   ```text
   git config --global user.email your_email
   ```

### Getting your own copy of the code

For this lab we will be utilizing a project that already exists and making our own copy of it. We will do this through a process call _forking_ and then _cloning_.

#### Forking the repository

1. In your browser, navigate to [https://github.com/odrodrig/app-modernization-plants-by-websphere-jee6](https://github.com/odrodrig/app-modernization-plants-by-websphere-jee6).
2. From here, we now want to create our own copy of this repo. Click on the **Fork** button near the upper right side of the page.

![fork](.gitbook/assets/fork.png)

1. When done, you will be taken to your own copy of the repo. Next, we need to clone the repo to have a local copy. 

#### Cloning a repo locally

Click on the green button on the right side of the repo that says _Clone or donwload_ and copy the URL that appears.

![clone url](.gitbook/assets/cloneurl.png)

1. Then, switch back to your web terminal. Enter the following command and ensure that your are in the **/data** directory:

   ```text
   pwd
   ```

![dataDir](.gitbook/assets/datadir.png)

1. Now let's clone the project. Enter the following command replacing _repo\_url_ with the url that your copied earlier.

   ```text
   git clone repo_url
   ```

![clone locally](.gitbook/assets/clonelocally.png)

Now that we have a local copy, we can develop on the app, make changes, and do whatever we need.

### Committing changes

In this section we will add a new file to our app, commit the changes, and push them out to GitHub. To do this, we will utilize the _git add_, _git commit_, and _git push_ commands.

1. From our web terminal, change directories into the repo we just cloned by using the following command:

   ```text
   cd app-modernization-plants-by-websphere-jee6/
   ```

![cd into repo](.gitbook/assets/cdappmod.png)

1. Now let's add a text file that we want to include in our repo. Enter the following command to create the empty file "test.txt".

   ```text
   touch test.txt
   ```

2. Next we need to stage our changes for our commit. Run the following command to stage all modified files in your working directory.

   ```text
   git add .
   ```

3. Then, we can commit our change. Remember that commit messages should be concise and descriptive. Run the following command to commit your change:

   ```text
   git commit -m "Added test.txt file"
   ```

4. Next push to GitHub by running the following command:

   ```text
   git push
   ```

5. Enter your GitHub password when asked.

![push](.gitbook/assets/push.png)

Your change has now been pushed to your remote repository on GitHub. In the next section, we will explore how we pull changes from the remote.

### Pulling changes locally

When working on a project in GitHub, it is pretty common to collaborate with other developers on the same repo. When one person pushes and merges changes into the repo, it is important for other collaborators to pull the new changes to their local repositories to get the latest additions. To simulate other developers making changes, we will be using the code editor on GitHub to make a change to our file and then pull the changes to our local repository.

1. In your browser, go back to your repo on GitHub.
2. Find and click on **test.txt** from your list of files.
3. Then, click on the pencil icon on the right side of the page to edit the file.

![edit](.gitbook/assets/edit.png)

1. You can use this editor to make simple changes to your files directly in GitHub. Let's go ahead and add some text to the file. Add a simple message like the following"

   ```text
   This file has been changed. Pull changes locally to get the latest version.
   ```

![short message](.gitbook/assets/shortmessage.png)

1. Then, enter a descriptive commit message and click on **Commit changes**

![commit changes](.gitbook/assets/commitchanges.png)

1. Now go back to your web terminal and run the following command

   ```text
   cat test.txt
   ```

Since we haven't pulled changes yet, nothing should show up.

1. To pull the latest changes and merge them into your local repository, run the following command:

   ```text
   git pull
   ```

![git pull](.gitbook/assets/gitpull.png)

1. Finally, to verify that the changes came through, run the following command to examine the contents of the file.

   ```text
   cat test.txt
   ```

You should see the short message that you added to the file in the GitHub editor is now printed to the terminal.

![test file text](.gitbook/assets/testtext.png)

## Conclusion

In this lab we covered forking our own copy of a repo and making a local clone of it. Then we added a new file, staged the change, committed, and then pushed to our remote repo on GitHub. Lastly, we made a change in the GitHub editor and pulled the change to our local repository.

Continue on to the next lab, working with Helm.

