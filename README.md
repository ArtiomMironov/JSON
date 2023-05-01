# JSON
github HW1
GitHub- Homework - 1 - JSON
This is a part of GIT homework 1. To see all the GIT homeworks, click here.

  Task:
1. Create a remote repository called JSON.
2. Clone the JSON repository to the local computer.
3. Create a new.json file inside the local JSON.
4. Add the file to Git.
5. Commit the file.
6. Send the file to a remote GitHub repository.
7. Edit the content of the file new.json - write information about yourself (full name, age, number of pets, future desired salary). Write everything in JSON format.
8. Send the changes to a remote repository.
9. Create a preferences.json file.
10. In the preferences.json file, add information about your preferences (favorite movie, favorite series, favorite food, favorite time of year, country you would like to visit) in JSON format.
11. Create a skills.json file, add information about skills that are going to be learned at the course in JSON format.
12. Send two files at once to remote repository.
13. Create the bug_report.json file on the web interface.
14. Save the changes at the web interface.
15. At the web interface, modify the bug_report.json file and add the bug report in JSON format.
16. Save the changes at the web interface.
17. Synchronize remote and local JSON repository.

STEPS

1. Create a remote repository called JSON.
To make this first step, I go to my GitHub account, then go to the "Repositories" tab and click on "New" button.

2. Clone the JSON repository to the local computer.
To clone the repo JSON, firstly I don't exit GitHub and copy the link to for a command in terminal. Then I go to Terminal CLI and create a folder e.g. GIT with mkdir command, this is where I'm going to clone the repo. I clone the remote repo to the working directory by typing a command and pasting the link:
% git clone https://github.com/ArtiomMironov/JSON.git
Now, we have a repository cloned locally and can add files. Note: this command creates a separate directory e.g. JSON where keeps the local repo.

3. Create a new.json file inside the local JSON.
Now, let's go to CLI:
% touch new.json

4. Add the file to Git.
To prepare the content for the commit to the remote repo, I typed:
% git add .
and checked if the changes are added with a git status command. The terminal showed as follows:

On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   new.json


5. Commit the file.
The next step is a commit. A commit is a kind of snapshot of changes, it has a special identifier, so you can come back and see. When you commit (git commit), you also add a message that helps you to summarize the changes we added (-m)
% git commit -m "blank new.json added"
[main (root-commit) 24c372e] blank new.json added               # here we can see the commit identifier 24c372e
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 new.json

6. Send the file to a remote GitHub repository.
We use git push command for sending the commit to the remote repo at GitHub and get the answer that the process is successfully done:
% git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 221 bytes | 221.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/ArtiomMironov/JSON.git
 * [new branch]      main -> main

7. Edit the content of the file new.json - write information about yourself (full name, age, number of pets, future desired salary). Write everything in JSON format.
I am using here the vim new.json to open vim editor and write the info e.g.:
{
  "FullName": "Mironov Artiom Andreech",
	"Age": 22,
	"Pets": 1,
	"Salary": 500
}

8. Send the changes to a remote repository.
As we have only 1 file to send to the remote repo, we can use either git add path/to/file command or just git add . to add all changes to prepare for a commit.
% git add .                                                         # adding the changes to Git, preparing for the commit

On branch main      
Your branch is up to date with 'origin/main'.               

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   new.json                                        # notification about file modification
Then:
% git commit -m "added information about myself to new.json"        # committing with an appropriate message

[main 24c372e] added information about myself to new.json  
 1 file changed, 8 insertions(+)
Finally, uploading the changes to the remote repo:
% git push                                                  

Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 354 bytes | 354.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/ArtiomMironov/JSON.git
   6928ae8..24c372e  main -> main

9. Create a preferences.json file.
As we out information to the file in the very next step, I straightly used vim to create the file and add info:
% vim preferences.json
Then press Insert to be able to modify our new json.

10. In the preferences.json file, add information about your preferences (favorite movie, favorite series, favorite food, favorite season, country you would like to visit) in JSON format.
Here, we use vim editor to type into a file:
{
	"FavouriteMovie": "IngloriousBastards",
	"FavouriteSeries": "GameOfThrones",
	"FavouriteFood": "Pizza",
	"FavouriteSeason": "Summer",
	"CounrtyWoulduWantToVisit": "Argentina"
}
Then press Esc and :wq to save and quit.

11. Create a skills.json file, add information about skills that are going to be learned at the course in JSON format.
Let's try a cat > command here as an option to create a file and type info right in the terminal:
% cat > skills.json
{
      "Skills": [
  "Writing Bash commands and simple scripts",
  "Working with GitHub and Git",
	"Understanding the most popular test design techniques",
  "Understanding client-server architectire",
  "API testing with Postman",
	"Writing test documentation",
	"Web and mobile testing with devtools",
	"iOS/Android traffic monitoring with Charles and Fiddler",
	"SQL basics",
	"JMeter load testing basics",
	"Developing simple mobile apps with Xcode/Android Studio"
      ]
}
After typing the last line, press Enter and Ctrl+C to save and quit. Note: I would recommend using spaces not Tabs here to feel more confident with managing the file structure.

12. Send two files at once to the remote repository.
As I already new some bash hacks, I can probably add, commit and push these new 2 files by one-line command using && operator. Note: && operator means "if the previous command has been successfully executed"
% git add . && git commit -m "adding preferences.json and skills.json" && git push
As a result, we have all three commands successfully executed.
[main 77bd9e0] adding preferences.json and skills.json
 2 files changed, 22 insertions(+)
 create mode 100644 preferences.json
 create mode 100644 skills.json
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 729 bytes | 182.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/ArtiomMironov/JSON.git
   e810d4d..77bd9e0  main -> main

12(a). Changing json files' keys to camelCase.
According to the Google Json Styles Guide, all the property names have to be camel-cased, so let's go back and try to change all our keys (example for new.json file below):
{
  "FullName": "Mironov Artiom Andreech",
	"Age": 22,
	"Pets": 1,
	"Salary": 500
}
Now, let's try to add and commit the changes of the files by another one-line command:
$ git commit -a -m "json change keys to camelCase"
[main 9aa97c8] json change keys to camelCase
 2 files changed, 8 insertions(+), 8 deletions(-)
Note: git commit -a -m allows us to add the changes and commit them at once. However, we can use this command ONLY in case we already have the files in our remote repo. Now, we only have to do git push for uploading the changes to the remote repository.

13. Create the bug_report.json file at the web interface.
This step means going to GitHub page and creating the file from there. Just add a new json file and write into the text editor:
{
  "ID": 62,
  "Severity": "minor",
  "Priority": "low",
  "Title": "The quiz answer options are displayed in English in the box [Test yourself] of the Block [Stock market exchanges] when languages DE, RO, DA, HU, SK, FI are selected ",
  "Environment": [
    "Windows 10 Chrome 112"
    ],
  "StepsToReproduce": [
    "1. Navigate to capital.com",
    "2. Click button Education on the dropdown Navbar",
    "3. Scroll down to the block Learn how to trade",
    "4. Click link 3 Stock market exchanges in the block Learn how to trade”,
    "5. Select the language DE, RO, DA, HU, SK, FI",
    ],
   "Precondition": "None",
   "ExpectedResult": "The quiz answers are displayed in the selected language",
   "ActualResult": "The quiz answer options are displayed in English",
   "Attachment": "(URL to the video)",
   "Postcondition": "None",
   "Reproducibility": "N/a",
   "Author": "ArtiomMironov"
}

14. Save the changes at the web interface.
Under the editor section, we have a section called "Commit new file" with a message and description input fields. I left the first input field as is, as it was proposed to have a message "Create bug_report.json". I also left the second input field empty as it is an optional extended description. Finally, there are radio buttons representing options of committing the file to main branch directly or creating a new separate branch for the JSON repo. I chose committing to the main branch. Then, just send this commit, and we're done 😄

15. At the web interface, modify the bug_report.json file and add the bug report in JSON format.
What if I see that I provided an incorrect ID for this bug report and want to set it as an integer? We can go to the file at GitHub and modify by opening the file and clicking on pencil icon 📝:
"id": 62,

16. Save the changes at the web interface.
Here, we do similar to the step 14. Commit message is also proposed: "Update bug_report.json", I changed it to "Update bug report ID in bug_report.json"

17. Synchronize remote and local JSON repository.
For this step, we go back to our terminal to type a git pull command. We mention which exact branch we want to be pulled to the local JSON repo:
% git pull origin main
As a result, we have command successfully executed, with a notification that our new file bug_report.json has been added.
' remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 6 (delta 2), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), 1.83 KiB | 25.00 KiB/s, done.
From https://github.com/ArtiomMironov/JSON
 * branch            main       -> FETCH_HEAD
   9aa97c8..e97fe8d  main       -> origin/main
Updating 9aa97c8..e97fe8d
Fast-forward
 bug_report.json | 25 +++++++++++++++++++++++++
 1 file changed, 25 insertions(+)
 create mode 100644 bug_report.json '

_Note: We can also make sure the file is added by using ls command (see the list of the files in working directory), or we can straightly open the new file by cat command.


