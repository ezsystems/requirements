#Form Builder M3 - Deleting a Form

## Introduction
This document describes how an Editor can delete a form from the Form Manager's user interface.


## Functional Specifications -  User stories


### User Stories

User Story ID | User Story Description
:------------ |:-------------
1             | ``` As a User, I should have the ability to select a form in the Form Manager for deletion ```
2             | ``` As a user, I should not be allowed to delete a form if the selected form is in use on the landing page ```
3             | ``` As a user, I should have the option to navigate to the landing page (in EDIT mode) when I try to delete a form in use on the landing page```
4				 | ``` As a user, I should be warned when deleting a form in the Form Manager if the form contains collected data```
5				 | ``` As a user, I should have the option to download collected data when I try to delete a form which contains collected data```
6             | ```As a user, I should be warned when deleting a form in the Form Manager```




## Functional Specifications -  Detailed behaviors

### User story 1 - As a User, I should have the ability to select a form in the Form Manager for deletion
*Changes to the current implementation include: <br /> 1. adding a radio button for each form in the table and <br /> 2. adding a 'Delete' button at the top right corner of the table. <br /><br /> By default (if forms exists), then no form will be selected and the 'Delete' button will be disabled.*

***Please refer to the attached image 'FormManagerwithDeleteOption.png'***

BDD ID  | BDD Scenario
:------ |:-------------
1       | **Given**: I am logged in<br /> AND I navigated to the Form Manager<br /> AND see a list of existing forms created on the website <br /> **When**: I click on a Radio button to select a form to delete <br /> **Then**: The ‘Delete’ button at the top of the table is enabled 


### User story 2 - As a user, I should not be allowed to delete a form if the selected form is in use on the landing page
*A user should not be able to delete a form which is still in use on a Landing page. User will have to first delete the form block on the landing page and then come back to the Form Manager in order to delete it from the list*

***Please refer to the attached image 'FormDeleteModalEditLandingPage.png'***

BDD ID  | BDD Scenario
:------ |:-------------
1		 | **Given**: I am logged in <br /> AND I navigated to the Form Manager<br /> AND I selected a Form which in in use on a landing page to delete from the list <br />**When**: I click on the Delete button <br /> **Then**: A modal window appears with a message (see below) and CTA buttons ('Edit Landing Page' and 'Cancel')

#### Message on the modal window
**You cannot delete this form because it is still in use** <br />
Please edit the %landing-page-name% landing page and remove the form block before deleting the form


### User story 3 - As a user, I should have the option to navigate to the landing page (EDIT mode) when I try to delete a form in use on the landing page


BDD ID  | BDD Scenario
:------ |:-------------
1		 |  **Given**: I am logged in <br /> AND I navigated to the Form Manager<br /> AND I selected a Form which in in use on a landing page to delete from the list <br /> AND I clicked on the delete button<br/>AND a modal window has opened with a message and CTA buttons ('Edit Landing Page' and 'Cancel')<br />**When**: I click on the button 'Edit Landing Page' <br /> **Then**: I will be re-directed to the corresponding landing page in the EDIT mode


### User story 4 - As a user, I should be warned when deleting a Form in the Form Manager if the form contains collected data
*A user will be asked for a confirmation when trying to delete a form which contains collected information. When confirmed, the form as well as the data is deleted from the Form Manager*

***Please refer to the attached image 'FormDeleteModalWhenConainsData.png'***

BDD ID  | BDD Scenario
:------ |:-------------
1		 | **Given**: I am logged in <br /> AND I navigated to the Form Manager<br /> AND I selected a form which is NOT in use on a landing page and contains collected data<br /> **When**: I click on the Delete button <br /> **Then**: A modal window appears with a message (see below) and CTA buttons ('Delete Form', 'Cancel' and 'Download Data')


#### Message on the modal window
**Are you sure you want to delete this form?** <br />
The collected data will be permanently deleted along with the form


### User story 5 - As a user, I should have the option to download collected data when I try to delete a form which contains collected data
*A user will be given an option to download the collected data as a CTA on the modal window*


BDD ID  | BDD Scenario
:------ |:-------------
1		 | **Given**: I am logged in <br /> AND I navigated to the Form Manager<br /> AND I selected a form which is NOT in use on a landing page and contains collected data<br />AND I clicked on the delete button<br/>AND a modal window has opened with a message and CTA buttons ('Delete Form', 'Cancel' and 'Download Data') <br />**When**: I click on the button 'Download Data'<br /> **Then**: A file in a CSV format is automatically downloaded to my computer


### User story 6 - As a user, I should be warned when deleting a form in the Form Manager

BDD ID  | BDD Scenario
:------ |:-------------
1		 |  **Given**: I am logged in <br /> AND I navigated to the Form Manager<br /> AND I selected a form which is NOT in use on a landing page and contains collected data<br />AND I clicked on the delete button<br/>AND a modal window has opened with a message and CTA buttons ('Delete Form','Cancel','Download Data') <br />**When**: I click on the button 'Delete Form'<br /> **Then**: The form and the data is permanently deleted from the Form Manager and will no longer be part of the form list 
2		 |  **Given**: I am logged in <br /> AND I navigated to the Form Manager<br /> AND I selected a form which is NOT in use on a landing page and DOES NOT contain collected data<br />AND I clicked on the delete button<br/>AND a modal window has opened with a message (see below) and CTA buttons ('Delete Form' and 'Cancel') <br />**When**: I click on the button 'Delete Form'<br /> **Then**: The form is permanently deleted from the Form Manager and will no longer be part of the form list

***Please refer to the attached image 'FormDeleteModal.png'***

#### Message on the modal window
**Are you sure you want to delete this form?** <br />
