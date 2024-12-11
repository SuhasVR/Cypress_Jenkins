# wmi-fe-cy-qe-automation

*A base template for FE E2E QE Cypress Cucumber Automation projects*

<br>

Currently front-end UI automation testing is being done using [Cypress](https://www.cypress.io/) v12.x.x along with [Cucumber](https://cucumber.io/) framework with [TypeScript](https://www.typescriptlang.org/)

<br>

### Softwares required for your local computer:

* [Node JS](https://nodejs.org/en/download/)
* [VSCode download](https://code.visualstudio.com/download)
* [Cypress download and system requirements](https://docs.cypress.io/guides/getting-started/installing-cypress)

<br>

Install cypress latest version
```
$ npm install cypress --save-dev
```
In case specific version should be installed define the version number in Cypress install command:

```
$ npm install --save-dev cypress@12.7.0
```


<br>

### Plugins required for Cucumber and Environment Variables in VSCode:

* [Cucumber (Gherkin) Full Support](https://marketplace.visualstudio.com/items?itemName=alexkrechik.cucumberautocomplete)
* [Dotenv Official +Vault](https://marketplace.visualstudio.com/items?itemName=dotenv.dotenv-vscode)

<br>

*After installing* Dotenv Official +Vault *plugin*: 

* Run this command in your terminal:
```
$ npm install --save-dev dotenv cypress-dotenv
```
* Create **.env** file in the root directory of the project.

```
# example .env file
URL = https://project-url/
USERNAME = anyusername
PASSWORD = anypassword

```
* To use env variables contact Test team to add the same environment variables to project GitLab repository. Contact Test team for this process as limited person granted access to add environment variables to GitLab repositories. Provide the environment variables you will use and the link of your GitLab repository.

<br>

**Note:**

The **.env** file must be ignored and already added to .gitignore file of this project. It should be remain the same and never exposed to the remote repository.

---
<br>

## To work on an existing project/repo:

* Have a folder configured on your local device with ‘git init’ command on terminal to prepare that folder for commits.
* Go to the repo on Gitlab, have an account setup with permission to access the project/repo, set up your SSH keys in user settings.
* Then go to the projects page on GitLab clone copy the ‘Clone with SSH’ link, open terminal and change directory to the newly configured folder and run git clone command

```
$ git clone {COPIED SSH LINK GOES HERE}
```
<br>

## Folder Structure For Cypress Test Setup (reference to v12.x.x)

On left tab there are folders, view **cypress\integration\features** Here you will see feature files that are labeled with ‘.feature’ at the end. In these files, using cucumber structure we have the overall feature, and we can add multiple scenarios for the various tests we want to perform that relate to that feature. You can create multiple feature files, and within each, can have multiple scenarios with cucumber integration.

In folder **cypress\PageObjects** we can create **.ts** files to store any locators we are interested in and call back to them in our step definition files, where the majority of our test steps are coded in cypress commands.
Those files are located in **cypress\support\step-definitions** Here we import key methods such as the **Given, And, When, Then, But, Before, After** for our cucumber integration and any other plugins/configurations needed before proceeding to create cypress commands for each step of that test.

<br>

## RUN CYPRESS TESTS/FEATURES WITH CUCUMBER INTEGRATION:

* Open Cypress Test Runner: Open terminal on vscode and run command: 

```
$ npx cypress open
```

Test Runner should be configured to allow you to select any feature file which will open a test browser and run the test script. You will be able to see what the browser looks like to the user as the test is run.
Additionally, you can select on top right section to run ALL integration features.
Lastly, to run in **headless** mode by this command: 

```
$ npx cypress run
```

<br>

## Cypress Documentation:

* [Cypress Official website](https://www.cypress.io/)
* [Cypress Github Documentation](https://github.com/cypress-io/cypress-documentation)